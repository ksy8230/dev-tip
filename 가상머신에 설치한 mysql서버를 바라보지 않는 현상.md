# 가상머신에 설치한 mysql서버를 바라보지 않는 현상

## 현상

가상머신에 mysql 디비서버를 설치하고 로컬피시(윈도우)에서 heidiSQL 클라이언트 프로그램을 사용하고팠다.(SQL문 어색어색...)  
그런데 가상머신에서 포트포워딩을 설정했음에도 가상머신의 디비 서버에 연결되지 않았다.
![캡처](https://user-images.githubusercontent.com/24996316/132281461-28be7cd4-a254-4b43-b918-8c5824840a89.JPG)

## 해결

로컬에서도 mysql이 설치되어있으면 가상머신sql과 로컬피시sql 서버가 충돌이 난다.

- 로컬피시 sql를 전부 삭제
- 외부(윈도우)에서 접속 가능하도록 가상머신 서버 파일 설정
  > vi /etc/mysql/mariadb.conf.d/50-server.cnf
  ```
  # bind-address           = 127.0.0.1
  ```
