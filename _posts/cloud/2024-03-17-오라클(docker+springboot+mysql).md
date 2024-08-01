---
title: 오라클(docker+springboot+mysql)
author: w
date: 2024-03-17 22:23:00 +0800
categories: [cloud, oracle]
tags: [practice, docker, mysql]
img_path: /assets/img/post/
---

## 오라클 클라우드에서 docker springboot mysql 구현

### 준비물
- 오라클 클라우드 인스턴트 생성 후 Putty나 MobaXterm으로 ssh키 접속
  - ubuntu 기본적인 세팅 -> [오라클 클라우드 세팅](/posts/오라클-클라우드-세팅/)
  - docker & docker-compose 설치 / 포트열기 -> [docker cli 모음](/posts/docker-cli-모음/)

### 명령어 모음
```bash
docker ps
docker ps -a
docker rm
docker image ls -a

docker-compose up
docker-compose up -d
docker-compose stop

docker exec -it mc mysql -u root -p

```

### 도커 컴포즈 작성
```yml
version: '3'
services:
  springboot:
    container_name: springboot
    image: openjdk:17
    ports:
      - "8080:8080"
    build:
      context: .
      dockerfile: springboot.dockerfile
    depends_on:
      - mysql
    environment:
      SPRING_DATASOURCE_URL: jdbc:mysql://mysql:3306?createDatabaseIfNotExist=true&useSSL=false&useUnicode=true&serverTimezone=Asia/Seoul
      SPRING_DATASOURCE_USERNAME: test
      SPRING_DATASOURCE_PASSWORD: 1234
  mysql:
    container_name: mysql
    image: mysql:8
    build:
      context: .
      dockerfile: mysql.dockerfile
    environment:
      MYSQL_ROOT_PASSWORD: 1234
      MYSQL_DATABASE: test
    ports:
      - "3306:3306"
    command:
      - "mysqld"
      - "--character-set-server=utf8mb4"
      - "--collation-server=utf8mb4_unicode_ci"
```

### 도커 파일 작성
```dockerfile
# 이미지버전 / 환경설정 / 초기화 db파일
FROM mysql:8.0
ENV MYSQL_ROOT_PASSWORD=1234
ENV MYSQL_DATABASE=test
COPY test.sql /docker-entrypoint-initdb.d/
```
```dockerfile
FROM openjdk:17
WORKDIR /app
COPY test /app/test
RUN chmod +x /app/re-LAF/gradlew
RUN /app/re-LAF/gradlew clean package
CMD ["java", "-jar", "/app/test/build/libs/test-0.0.1-SNAPSHOT.jar"]
```
