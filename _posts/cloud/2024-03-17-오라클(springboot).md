---
title: 오라클(springboot)
author: w
date: 2024-03-17 10:23:00 +0800
categories: [cloud, oracle]
tags: [practice, docker, mysql]
img_path: /assets/img/post/
---

## 오라클 클라우드에서 springboot 구현

### 준비물
- 오라클 클라우드 인스턴트 생성 후 Putty나 MobaXterm으로 ssh키 접속
  - ubuntu 기본적인 세팅 -> [오라클 클라우드 세팅](/posts/오라클-클라우드-세팅/)
  - docker & docker-compose 설치 / 포트열기 -> [docker cls 모음](/posts/docker-cls-모음/)
  - java 설치 후 환경 세팅
    - sudo apt update
    - sudo apt install openjdk-17-jdk : 버전 하나만 설치하면 자동으로 환경변수설정됨
    - update-java-alternatives -l : 위치확인
    - sudo nano /etc/environment : 편집기 nano이용 수정 종료는 ctrl+x Enter
    - JAVA_HOME="/usr/lib/jvm/java-17-openjdk-amd64" : 끝에 추가
    - source /etc/environment 또는 재부팅 
    - echo $JAVA_HOME : 확인
    - java -version


### 순서
1. git clone 주소
2. chmod +x /app/project/gradlew : 권한설정
3. sudo /app/project/gradlew build -x test : 빌드
4. sudo java -jar /app/project/build/libs/project-0.0.1-SNAPSHOT.jar : 실행
5. sudo nohup java -jar /app/LAF/build/libs/project-0.0.1-SNAPSHOT.jar > /dev/null 2>&1 & : 백그라운드 실행
6. sudo ps -ef | grep project-0.0.1-SNAPSHOT.jar : 실행확인
7. sudo kill <PID> : 끄기