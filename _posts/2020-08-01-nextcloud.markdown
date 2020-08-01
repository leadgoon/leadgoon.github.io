---
layout: post
title: Nextcloud 도커 컨테이너 설치하기
tags: [Nextcloud, 도커, 라즈베리파이, 클라우드]
---

# Nextcloud 설치하기

넥스트 클라우드는 기본적인 데이터베이스로 SQLite를 내장하고 있지만, SQLite는 최소 및 개발 목적의 인스턴스만 사용하는 것을 추천한다. 실제 업무에 사룡하려면 다른 데이터베이스 백엔드를 사용하여야 하며, 이번 포스트에서는 별도의 외부 데이터베이스 설정 없이 기본만 다루기로 함. 

라즈베리파이에 nextcloud 도커 컨테이너를 올려서 클라우드를 만들어보자. 

도커 컨테이너 생성 전에 필요한 디렉토리를 생성하자

```
sudo mkdir -p /data/nextcloud/nextcloud
sudo mkdir -p /data/nextcloud/apps
sudo mkdir -p /data/nextcloud/config
sudo mkdir -p /data/nextcloud/data
sudo mkdir -p /data/nextcloud/theme
```

별도의 디렉토리가 필요한 이유는 도커 내장 디렉토리를 설정하게 되면, 
도커 컨테이너 삭제할 때 데이터도 전부 삭제된다는 점 때문이다. 

```
sudo docker run -d \
-p 8080:80 \
--name=nextcloud \
--restart=unless-stopped \
-v /data/nextcloud/nextcloud:/var/www/html \
-v /data/nextcloud/apps:/var/www/html/custom_apps \
-v /data/nextcloud/config:/var/www/html/config \
-v /data/nextcloud/data:/var/www/html/data \
-v /data/nextcloud/theme:/var/www/html/themes \
nextcloud
```

80포트를 많이 쓰기 때문에 80포트로 하였고, 원하는 포트로 변경해주면 됩니다. 
위에서 만든 폴더를 지정하고 실행하면 Nextcloud 컨테이너가 생성되고
IP:port 로 접속한 후 설정하여 사용한다. 

컨테이너 생성 후 2~3분 지나면 접속이 가능한데, 
웹페이지에서 관리자 ID / PASSWORD 설정하고 접속해서 사용하면 된다. 



