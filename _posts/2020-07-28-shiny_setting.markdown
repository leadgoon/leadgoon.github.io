---
layout: post
title: R shiny App을 웹호스팅하기
tags: [R Shiny 호스팅]
---

R shiny App을 만든 후 R-studio 에서 실행하면 로컬 IP인 127.0.0.1 로 실행하게 된다. 
options() 함수를 사용하여 IP주소와 PORT를 지정하여 외부로 호스팅할 수 있게된다. 

# R Shiny 호스팅하기

샤이니 서버 포트 지정

```r
options(shiny.port = 7775)
options(shiny.host = "112.100.45.50")
shinyApp(ui = ui, server = server)
```

또는

```r
runApp("test/app.R", host = "112.100.45.50", port = 8888)
```


# Blogdown 호스팅하기


사이트 빌드 하기
```r
build_site()
```

빌드한 사이트 지우기
```r
clean_site()
```

IP주소 및 포트설정
```r
host = '112.100.45.50'
port = '8080'
hugo_server(host, port)
```

새로운 포스트 만들기
```r
new_post("new", ext = '.Rmd')
```


# Plumber 로 API 제공하기

plumber.R 파일을 plumb() 함수로 배포하고, $run 옵션을 통해 포트를 지정한다. 

```r
plumber::plumb("test_API/plumber.R")$run(host = "112.100.45.50", port = 5762)
```



