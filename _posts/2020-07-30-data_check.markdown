---
layout: post
title: R 에서 파일 크기, 행 갯수, 열 갯수 확인하기
tags: [R 파일크기, 행 갯수, 열 갯수]
---


# R에서 데이터 체크하기

읽어 들인 데이터의 크기, 행 수, 열 수를 알아내기 위한 함수

```r
str(x)  # 데이터 구조 확인
nrow(x)  # 데이터 행 수
nccol(x)  # 데이터 열 수
object.size(x)  # 데이터 크기 (byte 단위)
format(object.size(x), units = "auto)  # 데이터 크기 (자동, Megabyte 단위)
```
