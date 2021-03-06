# 다이나믹 프로그래밍 (DP)

- 간단한 작은 문제들 속에서 '계속 반복되는 연산'을 활용하여 빠르게 풀 수 있는 것이 핵심
- 조건
  - 작은 문제에서 반복이 일어남
  - 같은 문제는 항상 정답이 같음
  - **메모이제이션으로 해결**
    - 한번 계산한 문제는 다시 계산하지 않도록 저장해두고 활용하는 방식

- 구현 방식
  - Bottom-up: 가장 작은 문제들부터 답을 구해가며 전체 문제의 답을 찾는 방식, 해결 용이 but 가독성 떨어짐, 함수 재귀 호출안하므로 시간과 메모리 사용량을 줄일 수 있음
  - Top-down: 가장 큰 문제를 방문 후 작은 문제를 호출하여 답을 찾는 방식 (재귀 방식), 메모이제이션 활용, 가독성 좋음 but 코드 작성이 힘듬, 점화식을 이해하기 쉽다는 장점

<br/>

<br/>

<br/>

> 참고
>
> https://semaph.tistory.com/16
>
> https://gyoogle.dev/blog/algorithm/Dynamic%20Programming.html