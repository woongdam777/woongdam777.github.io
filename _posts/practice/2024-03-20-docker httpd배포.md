---
title: docker httpd 배포
author: w
date: 2024-03-20 09:53:00 +0800
categories: [practice, toyproject]
tags: [toyproject, canvs, js]
---

## cli
```bash
docker run -d -p 80:80 --name httpd -v /path/to/your/html:/usr/local/apache2/htdocs httpd:latest

docker run -d -p 80:80 --name httpd -v /home/ubuntu/test/canvs:/usr/local/apache2/htdocs httpd:latest
```

도커를 실행하는데
- -d : 백그라운드
- -p 80:80 : 호스트랑 도커랑 포트매칭
- --name : 컨테이너 별명
- -v : 호스트 폴더랑 도커 폴더랑 마운트, 연결
- httpd:latest : 도커 서버에 있는 최신버전 apache httpd 서버 이미지 파일
