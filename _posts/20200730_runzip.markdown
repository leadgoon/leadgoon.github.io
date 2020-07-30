---
layout: post
title: R 에서 폴더생성, 파일다운, 압축풀기
tags: [R 파일다운, 압출풀기, 폴더생성]
---

# R studio 에서 파일 디렉토리 생성하고, 파일 다운로드하고, 압축풀기

인터넷 창에서 파일 다운받고, 파일탐색기를 통해 복사 후, 압축 푸는 과정을 코드화 하면 간편할 때가 있다. 
CLI 인터페이스의 장점으로 과거에 반복했던 작업을 다시 하지 않을 수 있어 좋다. 


- 디렉토리 생성
```r
dir.create('SHP/')
```

- 파일 다운로드
```r
download.file(url = "http://www.gisdeveloper.co.kr/download/admin_shp/SIG_201905.zip",
              destfile = "SHP/SIG_201905.zip")
download.file(url = "http://www.gisdeveloper.co.kr/download/admin_shp/EMD_201905.zip",
              destfile = "SHP/END_201905.zip")
```


- 압축 풀기
```r
unzip(zipfile = "SHP/SIG_201905.zip", exdir = "SHP")
unzip(zipfile = "SHP/END_201905.zip", exdir = "SHP")
```
