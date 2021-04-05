### CORS (Cross Origin Resource Sharing)



#### CORS 란?

- 브라우저 간의 데이터를 주고받는 과정에서
- 도메인 이름이 서로 다른 사이트 간에 api 요청을 할 때, 공유를 설정하지 않았다면 발생하는 에러



#### 해결 방법

- 데이터를 주고 받는 API 요청을 할 때

- 요청을 주는 쪽의 request 헤더와 요청을 받는 쪽의 response 헤더에

- 특정 값을 설정하면 됨

- EX) foo.com <-------------> bar.com

  - --------- Origin: foo.com ----------> (request 헤더에 **Origin**)

  - <---- Access-Control-Allow-Origin: foo.com -----

     (response 헤더에 **Access-Control-Allow-Origin**)

  - if) **Access-Control-Allow-Origin: *** 이면, 모든 origin에 대해 리소스 교환을 허용하겠다는 뜻



#### POST 요청의 CORS 해결책

- 만약, 이러한 상황이라면

- EX) foo.com <-------------> bar.com

- --------- Origin: foo.com ----------> (request 헤더에 **Origin**)

- <---- Access-Control-Allow-Origin: zoo.com ----- 

  (response 헤더에 **Access-Control-Allow-Origin**)

- 받는 쪽에서는 받은 요청을 바탕으로 허용된 도메인인지 아닌지를 ACAO 헤더에 정보를 담아서, 요청한 브라우저로 보냄

- 브라우저는 이걸 바탕으로 CORS 에러 낼지, 받은 요청 허용할지 결정함

- **Post 요청인 경우, 요청이 허용되지 않은 도메인임에도 불구하고 서버자원을 변경시킬 수 있음**

- 따라서, **요청에 앞서 Option으로 요청을 한번 더 보냄 (handshake 절차, 서로 다른 도메인 간의 요청이 허용되는지 확인)**





> 참고
>
> https://zzossig.io/posts/web/what_is_cors/