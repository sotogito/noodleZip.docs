total_value만

- 누적형
- 단발성
- 추가 옵션형


### 1 : table_badge_category / is_event
- 누적형 : 0
- 이벤트형 : 1

#### 2 : tbl_badge
- 기본 count형
- 추가 옵션형

##### 3
- 누적 저장형
- 점수만 업데이트형


어느 정도까지 정의를 해둬야할까
예를들어 라멘, 지역 을 사용하는 배지도 따로 정의를 안해두고 로직에서 처리하는데
그럼 단발성인지와 누적 저장이 되는지를 테이블에 넣으면 위에와 모순이 되는 일관성이 없는 데이터 정의인거같다.
어느 수준까지 배지에 대한 정보를 저장할지를 기준잡아야하낟.

---
1. 단발형 : null, 1
2. 레벨형 : null, 1
3. 단발 횟수 누적형 : 1, 1
4. 레벨 횟수 누적형 : 1, 1
()

enum으로 넣고
초기 total_value값
레벨업 


그냥 레벨 추가
위에 enum 받아서 분기처리

옵션형

REVIEW_GET_LIKE_COUNT_BADGE(1),  : 레벨형
COMMUNITY_GET_LIKE_COUNT_BADGE(2),  : 레벨형
ALL_COMMUNITY_POST_COUNT_BADGE(3),  : 레벨형
ALL_COMMENT_POST_COUNT_BADGE(4),  : 레벨형
RAMEN_REVIEW_REGION_BADGE(5),   :  레벨 횟수 누적형
RAMEN_REVIEW_CATEGORY_BADGE(6); :  레벨 횟수 누적형



그러면 prcess에서 처리하기 전에 
### 초기 배지 생성
1. 찾아온 배지가 없을 경우
2.  레벨 초기값으로 업데이트
### 레벨 업데이트
1. current_score하고 completion_value가 같은지 확인
2. 같으면 다음 레벨 초기값으로 업데이트