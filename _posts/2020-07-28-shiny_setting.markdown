# R Shiny 호스팅하기

샤이니 서버 포트 지정

options(shiny.port = 7775)
options(shiny.host = "112.100.45.50")
shinyApp(ui = ui, server = server)

또는

runApp("test/app.R", host = "112.100.45.50", port = 8888)
