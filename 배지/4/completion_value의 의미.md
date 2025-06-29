- 나는 지금까지 누적이 되는건줄알았다. 근데 아니었다.
- 각각의 배지의 독립적인 점수였다.
- 그럼 누적 횟수를...
CREATE TABLE `tbl_user_badge` (
  `user_badge_id` bigint NOT NULL AUTO_INCREMENT,
  `user_id` bigint NOT NULL,
  `badge_id` bigint NOT NULL,
  `current_score` int NOT NULL DEFAULT '1',
  `post_status` varchar(30) NOT NULL COMMENT '게시/숨김/즐겨찾기(프로필노출)',
  `created_at` datetime NOT NULL,
  `updated_at` datetime DEFAULT NULL,
  `obtained_at` datetime DEFAULT NULL,
  `total_value` int DEFAULT NULL,
  PRIMARY KEY (`user_badge_id`)
) ENGINE=InnoDB AUTO_INCREMENT=15 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci

current_score : 레벨업을 위한 점수

total_value : 총 기록을 저장해야할 경우

예를들어 지역별, 카테고리별 배지는 둘 다 저장을 해야된다.