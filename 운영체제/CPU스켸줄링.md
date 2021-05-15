## CPU 스켸줄링

### 스켸줄링

- CPU를 오버헤드 적게, 사용률 높게, 기아현상 적게 사용하기 위해 프로세스를 잘 배정하는 것

- 선점 : OS가 CPU의 사용권을 선점할 수 있는 경우, 강제 회수하는 경우

  비선점 : 프로세스 종료 or I/O 등의 이벤트가 있을 때까지 실행 보장 (처리시간 예측이 어려움)



### CPU 스켸줄링 종류

- 비선점
  - FCFS (First Come First Served)
    - 큐에 도착한 순서대로 CPU 할당
    - 실행 시간이 짧은 게 뒤로 가면 평균 대기 시간이 길어짐
  - SJF (Shortest Job First)
    - 수행시간이 가장 짧다고 판단되는 작업을 먼저 수행
    - FCFS 보다 평균 대기 시간 감소, 짧은 작업에 유리함
  - HRN (Highest Reponse-ratio Next)
    - 우선순위를 계산하여 점유 불평등을 보완한 방법 (SJF의 단점 보완)
    - 우선순위 = (대기시간 + 실행시간) / 실행시간



- 선점

  - Priority Scheduling

    - 우선순위 높은 대로 처리
    - 기아 현상 발생 가능 (실행 준비는 되었으나 CPU를 사용 못하는 프로세스)
    - Aging 방법으로 기아현상 문제 해결 가능 (아무리 우선순위가 낮은 프로세스라도 오래 기다리면 우선순위를 높여주자. 레디큐를 주기적으로 조사)

  - Round Robin

    - FCFS에 의해 프로세스들이 보내지면 각 프로세스는 동일한 시간의 Time Quantum만큼 CPU를 할당 받음 (Time Quantum || Time Slice -> 실행의 최소 단위 시간)

    - 할당 시간이 지나면 프로세스는 선점 당하고 레디큐의 제일 뒤에 가서 다시 줄 섬

    - `Time Quantum`이 크면 FCFS와 같게 되고, 작으면 문맥 교환이 잦아져서 오버헤드 증가

      cf. context switching overhead?

      ​	이전 실행되던 프로세스의 모든 상태를 PCB에 저장 & 

      ​	실행할 프로세스에 있는 내용 다시 로드할 때 소요되는 시간

  - Multilevel-Queue (다단계 큐)

    - Ready Queue를 여러개로 분할 (독립적인 스켸줄링 알고리즘을 가지는..)

    - 작업들을 여러 종류의 그룹으로 나누어 여러 개의 큐를 이용하는 방법

    - 우선순위가 낮은 큐들이 실행 못하는 걸 방지하고자

    - 각 큐마다 다른 `Time Quantum`을 설정 해주는 방식 사용

    - 우선순위가 높은 큐는 작은 Time Quantum 할당

      우선순위가 낮은 큐는 큰 Time Quantum 할당

  - Multilevel-Feedback-Queue (다단계 피드백 큐)

    - 주어진 Time Quantum동안 모두 CPU를 사용한 프로세스는 우선순위 감소

      주어진 Time Quantum동안 모두 CPU를 사용하지 않은 프로세스는 우선순위 증가

    - 입출력 위주 (=인터럽트가 잦은) 작업에 우선권을 줌
    - 처리시간이 짧은 프로세스를 먼저 처리하기 때문에 Turnaround평균 시간을 줄여줌



### CPU 스켸줄링 척도

- Response Time
  - 작업이 처음 실행되기까지 걸린 시간
- Turnaround Time
  - 실행 시간과 대기 시간을 모두 합한 시간 (작업이 완료될 때까지 걸린 시간)









<br/>

<br/>

<br/>

<br/>

> 참고
>
> https://github.com/gyoogle/tech-interview-for-developer/blob/master/Computer%20Science/Operating%20System/CPU%20Scheduling.md
>
> https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/OS#%ED%94%84%EB%A1%9C%EC%84%B8%EC%8A%A4%EC%99%80-%EC%8A%A4%EB%A0%88%EB%93%9C%EC%9D%98-%EC%B0%A8%EC%9D%B4