### 🔹 `@Transactional`

java

복사편집

`@Transactional public void updateBadge(Long badgeId) {     Badge badge = badgeRepository.findById(badgeId).get();     badge.setName("변경됨"); // dirty checking } // → 트랜잭션 커밋 시 flush & update 쿼리 실행`

- **쓰기 가능**
    
- 영속성 컨텍스트(1차 캐시)에 변경 내역을 추적하고,
    
- 트랜잭션 커밋 시 `flush` 해서 DB update 수행.
    

---

### 🔹 `@Transactional(readOnly = true)`

java

복사편집

`@Transactional(readOnly = true) public Badge getBadge(Long badgeId) {     return badgeRepository.findById(badgeId).get(); }`

- **쓰기 불가능 (flush 수행 안 함)**
    
- 조회 전용
    
- JPA가 스냅샷을 유지하지 않아 dirty checking 자체를 생략 → **성능이 조금 더 빠름**.
    

> 🚨 즉, 이 안에서 `badge.setName("변경됨")` 해도  
> **트랜잭션 커밋 시 update 쿼리 안 날림.**