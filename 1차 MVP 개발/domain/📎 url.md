#### /mypage/my
- `/mypage/my/saved-store/list` : 자신의 저장 가게 조회, 저장 가게 카테고리 수정 가능


---
#### /mypage/{userId}
- `/mypage/{userId}/saved-store/list` : 타인의 저장 가게 조회

---
##### 공통 사용 - 자신의 페이지에서 수정 없이 오직 조회의 목적만 가지고 있는 페이지
- `/mypage/{userId}/badges/list` : 자신, 타인의 배지 목록 조회

---
#### 2025/07/12
처음에는 자기 저산 페이지 조회를 /my로 설정하면 되겠다 생가갷ㅆ느데, 배지, 저장가게, 구독들이 마이ㅍ페이지 가위기능이 아니란걸 꺠닫고 뭔가 이상하다는걸 느쪘다.

1. 마이페이지
2. 배지
3. 저장가게
4. 구독 (팔로워 조회 default)
5. 내가 쓴 게시글 조회
6. 내가 단 댓글 조회
7. 내가 좋아요한 게시글 조회

#### 1. /mypage/{userId}

#### 2. /users/{userId}/badges

#### 3. /users/{userId}/saved-stores
#### 4. /users/{userId}/follower
- /users/{userId}/following
#### 5. /users/{userId}/boards
#### 6. /users/{userId}/comments
#### 7. /users/{userId}/liked-boards
