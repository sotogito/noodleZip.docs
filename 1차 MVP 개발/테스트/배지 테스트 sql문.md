
```
INSERT INTO tbl_user  
(login_id, password, user_name, email, user_type, active_status, is_email_verified, created_at)  
VALUES  
    ('user1', 'pass1', '사용자1', 'user1@example.com', '일반', '정상', 0, NOW()),  
    ('user2', 'pass2', '사용자2', 'user2@example.com', '일반', '정상', 0, NOW());  
  
  
  
  
INSERT INTO tbl_ramen_category  
(ramen_category_id, category_name, created_at, updated_at)  
VALUES  
    (1, 'A 카테고리', NOW(), NULL),  
    (2, 'B 카테고리', NOW(), NULL);  
  
  
  
  
INSERT INTO tbl_badge_group (badge_group_name) VALUES ('그룹1');  
INSERT INTO tbl_badge_group (badge_group_name) VALUES ('그룹2');  
  
  
  
  
INSERT INTO tbl_badge_category  
(badge_category_id, badge_group_id, badge_category_name, badge_description, is_active, event_start_at, event_end_at, badge_strategy)  
VALUES  
    (1, 1, '단일 배지', '단일 획득형 배지 (SINGLE)', 1, NULL, NULL, 'SINGLE'),  
    (2, 1, '누적 단일 배지', '누적형 단일 획득 배지 (SINGLE_ACCUMULATIVE)', 1, NULL, NULL, 'SINGLE_ACCUMULATIVE'),  
    (3, 2, '레벨 배지', '레벨 상승형 배지 (LEVEL)', 1, NULL, NULL, 'LEVEL'),  
    (4, 1, '누적 레벨 배지', '누적형 레벨 상승 배지 (LEVEL_ACCUMULATIVE)', 1, NULL, NULL, 'LEVEL_ACCUMULATIVE'),  
    (5, 2, '라멘 리뷰 지역 배지', '라멘 지역 리뷰 배지', 1, NULL, NULL, 'LEVEL_ACCUMULATIVE'),  
    (6, 2, '라멘 리뷰 카테고리 배지', '라멘 카테고리 리뷰 배지', 1, NULL, NULL, 'LEVEL_ACCUMULATIVE');  
  
  
  
  
  
-- 레벨 배지  
INSERT INTO tbl_badge  
(badge_category_id, badge_name, badge_level, completion_value, created_at, updated_at)  
VALUES  
    (3, '레벨 배지 1단계', 1, 1, NOW(), NULL),  
    (3, '레벨 배지 2단계', 2, 2, NOW(), NULL),  
    (3, '레벨 배지 3단계', 3, 3, NOW(), NULL);  
  
-- 누적 레벨 배지  
INSERT INTO tbl_badge  
(badge_category_id, badge_name, badge_level, completion_value, created_at, updated_at)  
VALUES  
    (4, '누적 레벨 배지 1단계', 1, 1, NOW(), NULL),  
    (4, '누적 레벨 배지 2단계', 2, 2, NOW(), NULL),  
    (4, '누적 레벨 배지 3단계', 3, 3, NOW(), NULL);  
  
-- 라멘 지역 배지  
INSERT INTO tbl_badge  
(badge_category_id, badge_name, badge_level, completion_value, created_at, updated_at, store_sido_legal_code)  
VALUES  
    (5, '라멘 지역 배지 서울', 1, 3, NOW(), NULL, 11),  
    (5, '라멘 지역 배지 부산', 1, 3, NOW(), NULL, 26);  
  
-- 라멘 카테고리 배지  
INSERT INTO tbl_badge  
(badge_category_id, badge_name, badge_level, completion_value, created_at, updated_at, ramen_category_id)  
VALUES  
    (6, '라멘 카테고리 배지 A', 1, 3, NOW(), NULL, 1),  
    (6, '라멘 카테고리 배지 B', 1, 3, NOW(), NULL, 2);

```
