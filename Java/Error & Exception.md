## 프로그램 오류

- 프로그램이 실행 중 어떤 원인에 의해서 오작동을 하거나 비정상적으로 종료되는 경우
- **Error**와 **Exception**으로 구분



## Error

<img src="https://github.com/GimunLee/tech-refrigerator/raw/master/Language/JAVA/resources/java-error-exception-003.png"/>

- 시스템 레벨에서 발생하여, 개발자가 조치할 수 없는 수준을 의미
- OutOfMemoryError : JVM에 설정된 메모리의 한계를 벗어난 상황일 때 발생. 힙사이즈가 부족하거나, 너무 많은 class를 로드할때, 가용가능한 swap이 없을때, 큰 메모리의 native메소드가 호출될때 등......
- **컴파일 시 문법적인 오류**와 **런타임 시 널포인트 참조와 같은 오류**로 프로세스에 심각한 문제를 야기시켜 프로세스를 종료 시킬 수 있음
- 발생하면 복구할 수 없는 심각한 오류 
- ex. 메모리 부족, 스택오버플로우



## Exception

<img src="https://github.com/GimunLee/tech-refrigerator/raw/master/Language/JAVA/resources/java-error-exception-002.png"/>

- 개발자가 구현한 로직에서 발생 (개발자가 처리가능) -> JVM은 정상 동작함!
- 컴퓨터 시스템의 동작 도중 예기치 않았던 이상 상태가 발생하여 수행 중인 프로그램이 영향을 받는 것
- ex. 연산 도중 넘침에 의해 발생한 끼어들기
- 발생하더라도 수습할 수 있는 비교적 덜 심각한 오류
- 프로그래머가 적절히 코드를 작성해주면 막을 수 있음
- Error 상황 방지하기 위해 Exception 상황 만들 수 있음
- ex. java에서는 try-catch문으로 Exception handling을 할 수 있음



## Exception의 2가지 종류

1. **Checked Exception**
   - 예외처리가 필수임 (<span style="color:orange">처리하지 않으면 컴파일 되지 않음</span>)
   - JVM 외부와 통신(네트워크, 파일시스템 등) 할 때 주로 쓰임
   - IOException, SQLException (RuntimeException이외에 있는 모든 예외)
2. **Unchecked Exception**
   - 컴파일 때 체크되지 않고, <span style="color:orange">Runtime에 발생하는 Exception</span>
   - NullPointerException, IndexOutOfBoundException (RuntimeException하위의 모든 예외)



## Exception Handling

- **JAVA에서 모든 예외가 발생하면 (XXX)Exception 객체를 생성함**

- <span style="color:red">예외 처리 방법 두가지</span>

  1. **try ~ catch** 

     예외에 대한 최종적인 책임을 지고 처리하는 방식

     try , catch (예외 발생시 수행할 로직, else if처럼 여러개 쓸 수 있음) , finally (마지막에 실행하고 싶은 로직)

  2. **throws Exception**

     발생한 예외의 책임을, 호출하는 쪽이 책임지도록 하는 방식 

     현재 메소드가 예외 처리 X 호출한 곳에다가 예외 발생 여부를 통보함

- 잘못된 하나로 인해 전체 시스템이 무너지는 결과를 방지하기 위한 기술적인 처리

- java에서는 예외와 에러도 객체로 처리

- 예외가 주로 발생하는 원인

  - 사용자의 잘못된 데이터 입력
  - 잘못된 연산
  - 개발자가 로직을 잘못 작성
  - 하드웨어, 네트워크 오작동
  - 시스템 과부하



## Throwable 클래스

<img src="https://github.com/GimunLee/tech-refrigerator/raw/master/Language/JAVA/resources/java-error-exception-001.png"/>



- Throwable 클래스는 예외처리를 할 수 있는 최상위 클래스
- Exception과 Error는 Throwable의 상속을 받음



## Exception 클래스 종류

- NullPointerException
  - Null 레퍼런스를 참조할 때 발생
- IndexOutOfBoundsException
  - 배열과 유사한 자료구조 (문자열, 배열, 자료구조)에서 범위를 벗어난 인덱스 사용
- ArthmeticException
  - 정수를 0으로 나눌 때 발생

<br/>

<br/>

<br/>

> 참고
>
> https://github.com/GimunLee/tech-refrigerator/blob/master/Language/JAVA/Error%20%26%20Exception.md#error--exception





