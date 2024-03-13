---
title: docker cls 모음
author: w
date: 2024-02-24 18:23:00 +0800
categories: [practice, docker]
tags: [practice, docker]
img_path: /assets/img/post/
---

젠킨스공부용
https://www.dongyeon1201.kr/9026133b-31be-4b58-bcc7-49abbe893044

도커공부용
https://www.dongyeon1201.kr/c20f7d07-6f23-4134-ae8e-e730dc7b5af6

도커가이드
https://www.lainyzine.com/ko/article/docker-tutorial-1/


## 리눅스(우분투)환경 docker 설치
```bash
curl -fsSL https://get.docker.com/ | sudo sh
sudo apt-get install docker.io
```
- curl: URL을 통해 데이터를 가져오는 명령줄 도구 / HTTP, HTTPS, FTP 등의 프로토콜을 지원
- fsSL: curl 명령에 사용되는 옵션
  - f: 서버가 응답하는 내용 중 2XX 이외의 상태 코드를 받았을 때 오류를 표시
  - s: 정적으로, 진행 상황이나 다운로드 정보를 출력하지 않음.
  - S: 오류가 발생한 경우 오류 메시지를 출력
  - L: 서버가 리디렉션을 보내면, 해당 위치로 따라간다.
- https://get.docker.com/: Docker 설치 스크립트를 호스팅하는 URL
- |: 파이프(파이프라인) 연산자로, 앞의 명령의 출력을 뒤의 명령의 입력으로 전달
- sudo: "superuser do"의 약어로, 특정 명령을 관리자 권한으로 실행
- sh: Bourne 쉘(Bourne shell) 스크립트를 실행하는 명령, 앞서 curl로 받은 스크립트를 실행

- sudo: "superuser do"의 약어, 특정 명령을 관리자 권한으로 실행
- apt-get: Advanced Packaging Tool의 명령줄 인터페이스, Ubuntu와 Debian 계열의 리눅스 배포판에서 패키지를 관리하는 도구
- install: 패키지 관리자를 통해 새로운 패키지를 설치하는 명령
- docker.io: Docker 패키지의 이름입니다. 이 명령은 패키지 관리자를 통해 Docker를 설치



```bash
docker <SUBCOMMAND> (<OPTIONS>)
docker run (<OPTIONS>) <IMAGENAME> (<COMMAND>)

docker ps
docker ps -a
docker image

docker stop <IMAGENAME>

```