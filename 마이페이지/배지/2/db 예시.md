#### tbl_badge_category
|badge_category_id|badge_category_name|is_event|category_group|badge_description|
|---|---|---|---|---|
|1|리뷰 좋아요 배지|false|LIKE|리뷰 좋아요 수에 따라 지급|
|2|게시글 좋아요 배지|false|LIKE|게시글 좋아요 수에 따라 지급|
|3|게시글 작성 수 배지|false|POST|게시글 누적 수에 따라 지급|
|4|댓글 작성 수 배지|false|POST|댓글 누적 수에 따라 지급|
|5|지역 라멘 리뷰 배지|false|REGION|지역별 리뷰 누적 수 기준|
|6|라멘 종류별 배지|false|RAMEN_CATEGORY|라멘 종류별 리뷰 수 기준|
|7|첫 리뷰 배지|true|(null)|매장 첫 리뷰 작성 시 지급|
|8|라멘집 개척자 배지|true|(null)|처음으로 매장 등록 시 지급|
|9|리뷰 100개 달성 배지|true|(null)|리뷰 총 수 100개 달성 시 지급|

#### tbl_badge
|badge_id|badge_category_id|badge_name|completion_value|badge_level|region_sido|ramen_category|active_status|
|---|---|---|---|---|---|---|---|
|101|1|좋아요 마스터 1단계|10|1|-|-|true|
|102|1|좋아요 마스터 2단계|30|2|-|-|true|
|201|2|커뮤니티 인기글러 1단계|10|1|-|-|true|
|301|3|면토커|10|1|-|-|true|
|302|3|면연재가|50|2|-|-|true|
|401|4|감칠맛 한마디|10|1|-|-|true|
|402|4|댓글장인|100|3|-|-|true|
|501|5|지역 지배자|15|3|SEOUL|-|true|
|601|6|중독자|35|3|-|돈코츠|true|
|701|7|첫 국물의 감동|1|1|-|-|true|
|801|8|라멘 개척자|1|1|-|-|true|
|901|9|리뷰 마스터|100|1|-|-|true|

#### tbl_user_badge
| user_badge_id | user_id | bedge_arch_id | current_value | post_status | obtained_at |
| ------------- | ------- | ------------- | ------------- | ----------- | ----------- |
| 1             | 1001    | 101           | 15            | 게시          | 2025-06-20  |
| 2             | 1001    | 301           | 10            | 게시          | 2025-06-21  |
| 3             | 1002    | 501           | 15            | 숨김          | 2025-06-22  |
| 4             | 1003    | 701           | 1             | 즐겨찾기        | 2025-06-23  |
| 5             | 1004    | 901           | 100           | 게시          | 2025-06-24  |