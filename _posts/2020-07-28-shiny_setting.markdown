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


