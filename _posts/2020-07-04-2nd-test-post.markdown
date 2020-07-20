---
layout: post
title: SSH 기본포트 변경하기
tags: [SSH 포트변경]
---

SSH란?
SSH는 리눅스 서버에 원격접속을 하도록 하는 프로그램을 말한다. 보통 22번 포트를 이용하여 통신을 하는데, 22번 포트가 알려진 포트이기 때문에 이를 변경해서 사용하는 것이 좋다. 일부 회사 보안 방침에 따라 22번 포트나 21번(주로 FTP) 포트로의 접근을 의도적으로 막아놓아서 접근이 불가능한 경우도 있다.

##### Step 1. 기본 포트 접속 테스트
windows 의 PowerShell 이나 CMD, 리눅스의 터미널창에서 다음과 같이 입력하여 접속 테스트를 한다. 
기본 포트가 22번 포트이기 때문에 -p [포트번호]를 입력하지 않으면, 자동으로 22번 포트를 사용해서 접속한다. 

> ssh -p [Port번호] [Username]@xxx.xxx.xxx.xxx (IP주소) 


##### Step 2. SSH 포트 변경 설정

ssh 접근 포트를 변경하기 위해 sshd_config 파일을 수정한다. 

> nano /etc/ssh/sshd_config


#Port 22 의 주석을 해제하고 원하는 포트 번호로 수정.

sshd 서비스 재시작

> service sshd restart


##### Step 3. SSH 접속 테스트

22번 포트로 ssh 접속
> ssh -p 22 [Username]@xxx.xxx.xxx.xxx (IP주소) 

8000번 포트로 ssh 접속
> ssh -p 8000 [Username]@xxx.xxx.xxx.xxx (IP주소) 

