#### 배지 페이지
user_id
- UserBadge 기준
- 조인 : Badge, BadgeCategory, BadgeGroup, RamenCategory
- 조건 : user_id가 같은, is_active가 true인

- BadgeGroup
	- badge_group_id
	- badge_group_name
- Badge
	- badge_id
	- badge_name
	- store_sido_legal_code -> string으로 변환 필요
	- ramen_category_id 로부터 ramen_cateogry_name
	- badge_image_url
- UserBadge
	- user_badge_id
	- accumulative_value
	- post_status

```
select
	ub.user_badge_id,
    ub.accumulative_value,
    ub.post_status,
    b.badge_id,
    b.badge_name,
    b.store_sido_legal_code,
    b.badge_image_url,
    rc.category_name,
    bg.badge_group_id,
    bg.badge_group_name
from
	tbl_user_badge ub
		join tbl_badge b on b.badge_id = ub.badge_id
        join tbl_badge_category bc on bc.badge_category_id = b.badge_category_id
        join tbl_badge_group bg on bg.badge_group_id = bc.badge_group_id
        left join tbl_ramen_category rc on rc.ramen_category_id = b.ramen_category_id
where
	ub.user_id = 1001
    and bc.is_active = 1
order by
	b.badge_level desc
limit 1;
```
-> 안됨

```
select
    t.user_badge_id,
    t.accumulative_value,
    t.post_status,
    t.badge_id,
    t.badge_name,
    t.badge_image_url,
    t.store_sido_legal_code,
    t.ramen_category_name,
    t.badge_group_id,
    t.badge_group_name
from (
    select
        ub.user_badge_id,
        ub.accumulative_value,
        ub.post_status,
        b.badge_id,
        b.badge_name,
        b.badge_image_url,
        b.store_sido_legal_code,
        rc.category_name as ramen_category_name,
        bg.badge_group_id,
        bg.badge_group_name,
        row_number() over (
            partition by bg.badge_group_id
            order by
                b.badge_level desc, -- NULL은 뒤로 밀림
                b.badge_id desc     -- 동일 level이면 최신
        ) as rn
    from
        tbl_user_badge ub
        join tbl_badge b on b.badge_id = ub.badge_id
        join tbl_badge_category bc on bc.badge_category_id = b.badge_category_id
        join tbl_badge_group bg on bg.badge_group_id = bc.badge_group_id
        left join tbl_ramen_category rc on rc.ramen_category_id = b.ramen_category_id
    where
        ub.user_id = 1001
) t
where t.rn = 1;
```

근데 이렇게 한번에 가져오려니ㅏ까
너무 길어서ㅜ 무섭고
성능도 안좋아지는거같다  
두단꼐로 나누기로 결심했다.  

1. 사용자가 가지고 있는 가장 높은 레벨의 배지 id만 가져오기
2. 그 배지들의 상세정보 dto에 담기
