## URI와 웹 브라우저 요청 흐름

### **URI (Uniform Resource Identifier)**

 <img src="./images/스크린샷 2021-04-12 오후 10.42.16.png">

- URL : 자원의 위치

  URN : 자원의 이름

------

<img src="./images/스크린샷 2021-04-12 오후 10.43.17.png">

------



### URI 단어 뜻

- **U**niform : 리소스를 식별하는 통일된 방식
- **R**esource : 자원, URI로 식별할 수 있는 모든 것 (제한 없음)
- **I**dentifier : 다른 항목과 구분하는데 필요한 정보



### URL, URN 단어 뜻

- URL - Locator : 리소스가 있는 위치를 지정
- URN - Name : 리소스에 이름을 부여
- 위치는 변할 수 있지만, 이름은 변하지 않음
- urn:isbn:8987098 (어떤 책의 isbn URN)
- URN 이름만으로 실제 리소스를 찾을 수 있는 방법이 보편화 되지 않음



### URL 전체 문법

<img src="./images/스크린샷 2021-04-12 오후 10.51.36.png">

- 프로토콜 (https)
- 호스트명 (www.google.com)
- 포트 번호 (443)
- 패스 (/search)
- 쿼리 파라미터 (q=hello&hl=ko)



#### URL scheme

- 주로 프로토콜 사용
  - 프로토콜? 어떤 방식으로 자원에 접근할 것인가 하는 클라이언트와 서버 간의 약속 규칙
  - ex. http, https, ftp 등
- http는 80 포트, https는 443 포트를 주로 사용, 포트는 생략 가능
- https는 http에 보안 추가 (HTTP Secure)



#### URL userinfo

- URL에 사용자 정보 포함해서 인증
- 거의 사용하지 않음



#### URL host

- 호스트명
- 도메인명 또는 IP 주소를 직접 사용가능
- ex. www.google.com



#### URL port

- 접속 포트
- 일반적으로 생략
- 생략 시, http = 80 / https = 443



#### URL path

- 리소스 경로 (path), 계층적 구조

- ex. /home/file1.jpg

  ​	 /members

  ​     /members/100

  ​	 /items/iphone12



#### URL query

- key=value 형태
- ?로 시작, &로 추가 가능 ex. ?keyA=value&keyB=valueB
- **query parameter**, **query string** 등으로 불림
- 웹 서버에 제공하는 파라미터
- 문자 형태



#### URL fragment

- https://docs.spring.io/spring-boot/doc/~~~~~~~/getting-started.html**#getting-started-introducing-spring-boot**
- html 내부 북마크 등에 사용
- 서버에 전송하는 정보 X





### **웹 브라우저 요청 흐름**

> https://www.google.com:443/search?q=hello&hl=ko

- DNS 조회 (IP: 200.200.200,2), HTTPS PORT 생략

- 웹 브라우저에서 HTTP 요청 메시지 생성

  <img src="./images/스크린샷 2021-04-12 오후 11.15.08.png">

- HTTP 메시지 전송

  <img src="./images/스크린샷 2021-04-12 오후 11.16.08.png">

  - TCP/IP패킷 = (전송데이터 ex.HTTP메시지) + 출발지 IP,PORT + 목적지 IP,PORT

- 요청 패킷 전달

- 구글 서버에서 TCP/IP패킷 까서 버리고, HTTP 메시지를 꺼냄 & 해석

- 구글 서버에서 HTTP 응답 메시지 만듬

  <img src="./images/스크린샷 2021-04-12 오후 11.19.22.png">

  - Content-Type: 응답 데이터의 형식
  - Content-Length: 실제 HTML 데이터의 길이

- 응답 패킷 전달 & 도착

- 웹 브라우저가 HTML 렌더링 

