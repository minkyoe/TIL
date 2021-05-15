## Thread

- 프로세스 내부의 CPU 수행 단위
- 같은 일을 하는 프로세스를 여러개 띄우면 메모리 낭비
  - **프로세스 하나에 CPU 수행 단위만 여러개 두고 있게 함**
  - **메모리 공간 하나만 띄우고 (프로세스 하나만 띄우고), 각 Program Counter가 code의 다른 부분 실행하게 함**

- 각 CPU 수행 단위마다 `현재 register에 어떤 값을 넣고`, `Program counter가 code의 어느 부분을 가르키며 실행하고 있는가`를 별도로 유지함
- Thread 하나가 Code 어느 부분을 실행하다가 함수 호출을 하면 함수 호출/리턴 관련 정보를 Stack에 저장



### Thread의 구성

> 각 Thread들이 독립적으로 가짐

1. Program Counter
2. Register set
3. Stack space



> Thread가 동료 Thread와 공유하는 부분 (task라고 부름)

1. Code section
2. Data section
3. OS resources



### Thread의 장점

- 응답성
  - 하나의 스레드가 blocked 상태인 동안에도 동일한 태스크 내의 다른 스레드가 실행되어 빠른 처리를 할 수 있음
  - ex. 스레드가 여러개인 웹 브라우저
- 자원 공유
  - Code, Data, 각종 자원을 Thread들이 공유하게 됨
  - 자원을 효율적으로 쓸 수 있음
- Economy
  - 새로운 프로세스 만드는 것보다 프로세스 안에 스레드 추가하는게 오버헤드가 적음
  - 프로세스 사이의 문맥 교환은 오버헤드가 큼 (CPU 관련 정보 저장, cache memory flush) vs. 프로세스 내부에서 thread 간 문맥 교환은 간단함 (동일한 주소공간을 쓰고 있기 때문. 대부분의 문맥은 그대로 사용할 수 있음)



<br/>

<br/>

<br/>

<br/>

> 참고
>
> https://minkyoe.tistory.com/21?category=898222