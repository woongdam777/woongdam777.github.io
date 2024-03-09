---
title: mysql백업 및 복원(docker)
author: w
date: 2024-03-09 16:23:00 +0800
categories: [practice, database]
tags: [practice, docker, mysql]
img_path: /assets/img/post/
---

## docker mysql백업 및 복원

### 백업 - 디비버로 쉽게 백업했음
```sql
mysqldump -u root -p db_name > db_name_backup.sql
```

### 복원 - 오라클서버/도커/mysql로 복원함

1. ssh로 서버 접속 후 백업파일 업로드 - 경로확인 pwd
2. 도커 컨테이너 mysql 실행 (컨테이명 mysql_ct)
3.
업로드한 파일 도커 컨테이너 안으로 복사
docker cp /home/ubuntu/backup/laf-20240309.sql mysql_ct:/
복사 잘 되었는지 확인
docker exec -it mysql_ct ls /

4. mysql 접속해서 database 생성
docker exet -it mysql_ct mysql -u root -p

CREATE DATABASE laf;

생성 되었는지 확인
SHOW DATABASES;

나가기 exit

5. mysql bash로 접속
docker exec -it mysql_ct bash

복원하기
mysql -u root -p laf < /laf-20240309.sql

6. mysql 재접속(한영 인식 가능하도록 utf8로 실행하기)
docker exec -it mysql_ct mysql -u root -p --default-character-set=utf8mb4

7. 복원확인
USE laf;
SHOW TABLES;
끝...
