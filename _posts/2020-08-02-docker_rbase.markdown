---
layout: post
title: R-base 도커 컨테이너 설치하기
tags: [R-base, 도커, 컨테이너, 라즈베리파이]
---

# R-Base 도커 컨테이너 만들기

R-Base 도커 컨테이너를 만들어보자. R-studio server 는 arm64 아키텍쳐를 지원하지 않으므로 라즈베리 파이에는 깔리지 않아 테스트 해볼수가 없음
다음에는 외부 데이터베이스에 nextcloud를 연동하여 클라우드 - 데이터베이스 - 데이터 분석 구조의 데이터 분석 시스템을 구축해 볼 수도 있음. 


즉시 테스트 환경은 아래와 같이 실행하면 새로운 컨테이너를 생성하여 운영체제로 들어갈 수 있다. 
그리고 r 을 입력하면 r-base 로 들어갈 수 있다. 
```
sudo docker run -ti --rm -v /data/nextcloud/data/leadgoon/files: r-base bash
```



현재는 클라우드 컨테이너 - 로컬 데이터 베이스 - R base 컨테이너 구조로 테스트 해보기 위함임
R-studio server 에서 개발하고, 

R-base 에서 배치모드로 실행되게 만든다면 자동화 분석도 가능할것 같다..

한번 연구해볼만함.


