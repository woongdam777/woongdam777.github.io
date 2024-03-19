---
title: 오라클(docker+mysql)
author: w
date: 2024-03-16 14:23:00 +0800
categories: [cloud, oracle]
tags: [practice, docker, mysql]
img_path: /assets/img/post/
---

## 오라클 클라우드에서 docker mysql 구현

### 준비물
- 오라클 클라우드 인스턴트 생성 후 Putty나 MobaXterm으로 ssh키 접속
  - ubuntu 기본적인 세팅 -> [오라클 클라우드 세팅](/posts/오라클-클라우드-세팅/)
  - docker & docker-compose 설치 / 포트열기 -> [docker cls 모음](/posts/docker-cls-모음/)

### 명령어 모음
```bash
docker ps
docker ps -a
docker rm
docker image ls -a

docker run -t
docker build -t mysql-image -f mysql.dockerfile .
docker run --name mysql-container -d -p 3306:3306 mysql-image

docker exec -it mc mysql -u root -p

```

### 도커 파일
```dockerfile
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=1234
ENV MYSQL_DATABASE=test
COPY test.sql /docker-entrypoint-initdb.d/
```