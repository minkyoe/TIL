## HashMap vs HashTable vs ConcurrentHashMap

> 공통점

- Collection의 Map 인터페이스를 구현한 클래스임
- key, value를 이용하여 값을 저장하는 구조임



> 차이점

1. HashTable

- 동기화를 지원함 -> **멀티 스레드 환경에서 사용할 수 있음**
- key, value에 Null을 허용하지 않음
- put, get과 같은 주요 메소드에 synchronized 키워드가 선언되어 있음



2. HashMap

- 동기화 지원 X (멀티 스레드 환경에 적합 X)
- key, value에 Null을 허용
- 주요 메소드에 synchronized 키워드 없음



3. ConcurrentHashMap

- HashMap에 ThreadSafe를 추가한 것

- 멀티 스레드 환경에서 HashMap을 동기화 시킨 Collections

- HashTable은 메소드 전체에 synchronized를 선언하는 반면

  ConcurrentHashMap은 동기화가 필요한 부분에만 동기화를 적용 (동기화에서 발생하는 오버헤드가 줄어듬)





<br/><br/><br/>

> 참고
>
> https://github.com/WooVictory/Ready-For-Tech-Interview/blob/master/Java/HashSet%20vs%20HashMap.md