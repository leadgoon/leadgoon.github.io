--
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
suo mkdir -p /data/nextcloud/apps
sudo mkdir -p /data/nextcloud/config
sudo mkdir -p /data/nextcloud/data
sudo mkdir -p /data/nextcloud/theme
```


