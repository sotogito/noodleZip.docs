1. limit절을 사용해야한다.
2. 안이쁘다  


일단 dsl레퍼지토리에서 사용할 인터페이스를 생성해준다.  
이름같은 경우는 보통 JPA 레퍼지토리가 Entity+Repository라면 dsl은 중간에 Query를 많이 넣는다 -> BadgeQueryRepository  
그리고 QueryDsl의 쿼리를 작성할 impl클래스를 생성해준다. -> BadgeQueryRepositoryImpl  
컨피그로 등록한 JPAQueryFactory를 가져와야하며, 레퍼지토리 어노테이션이 필요하다.  


### BadgeRepository
-  jpql
```
@Query("""  
        select b        
        from Badge b        
        where b.badgeCategory.id =:badgeCategoryId        
        order by b.badgePolicy.badgeLevel asc        
        """)  
List<Badge> findMinLevelBadgeByBadgeCategoryId(Long badgeCategoryId, Pageable pageable);
```
- queryDSL
```java
public Optional<Badge> getInitDefaultLevelBadge(Long badgeCategoryId) {  
    QBadge badge = QBadge.badge;  
  
    return Optional.ofNullable(queryFactory  
            .selectFrom(badge)  
            .where(badge.badgeCategory.id.eq(badgeCategoryId))  
            .orderBy(badge.badgePolicy.badgeLevel.asc())  
            .limit(1)  
            .fetchOne());  
}
```

```
return queryFactory  
        .selectFrom(badge)  
        .where(badge.badgeCategory.id.eq(badgeCategoryId))  
        .orderBy(badge.badgePolicy.badgeLevel.asc())  
        .stream().limit(1)  
        .findFirst();
```
처음에는 위와같이 작성했는데 `.stream().limit(1).findFirst()`은 자바 메모리에서 제한하는 것으로 일단 db에서 Limit제한 없이 다 가져온다. 즉 db에서 다 가져오고 자바에서 스트림으로 하나만 처리해서 가져오는 구조라서 불필요하다.  

또한 

| 메서드                      | 설명                        | 언제 사용?                          |
| ------------------------ | ------------------------- | ------------------------------- |
| `fetchOne()` / `fetch()` | 단순 조회                     | ✅ 기본값으로 연관 객체는 **지연 로딩(LAZY)**  |
| `fetchJoin()`            | 연관된 엔티티를 **즉시 로딩(EAGER)** | ❗정말 그 연관 객체까지 한 번에 가져와야 할 때만 사용 |
- 라멘 카테고리 배지 조회
```
@Query("""  
        select b        
        from Badge b        
        where b.badgeCategory.id =:badgeCategoryId        
        and b.badgeExtraOption.ramenCategory.id =:ramenCategoryId        
        order by b.badgePolicy.badgeLevel asc        
        """)  
List<Badge> findMinLevelBadgeByBadgeCategoryIdAndRamenCategoryId(  
        Long badgeCategoryId,  
        int ramenCategoryId,  
        Pageable pageable  
);
```

```java
public Optional<Badge> findInitRamenCategoryLevelBadge(Long badgeCategoryId, int ramenCategoryId) {  
    QBadge badge = QBadge.badge;  
    QCategory ramenCategory = badge.badgeExtraOption.ramenCategory;  
  
    return Optional.ofNullable(  
            queryFactory  
                    .selectFrom(badge)  
                    .where(  
                            badge.badgeCategory.id.eq(badgeCategoryId),  
                            ramenCategory.id.eq(ramenCategoryId)  
                    )  
                    .orderBy(badge.badgePolicy.badgeLevel.asc())  
                    .limit(1)  
                    .fetchOne()  
    );  
}
```
