# Spanning Tree

- **그래프 내의 모든 정점을 포함**하는 트리
- 그래프의 **최소 연결 부분 그래프**
  - 최소연결 = 간선의 수가 가장 적음
  - 정점이 n개 일 때, 그래프의 최소 간선수 = n-1
  - **n-1개의 간선으로 연결**되어 있으면 트리형태가 됨, 스패닝 트리!
- 그래프 일부 간선을 선택해서 만든 트리
- **모든 정점들이 연결되어 있어야함**
- **사이클을 포함해서는 안됨**





# MST (Minimum Spanning Tree)

- Spanning Tree 중에서 **사용된 간선들의 가중치 합이 최소인 트리**
  - 간선의 가중치의 합이 최소여야함
  - n개의 정점을 가지는 그래프에서 반드시 n-1개만의 간선을 사용해야함
  - 사이클에 포함되어서는 안됨



### Kruskal 알고리즘

- 탐욕적인 방법 사용
  - 결정을 해야할 때마다 그 순간에 가장 좋다고 생각되는 것을 선택함으로써 최종적인 해답에 도달하는 것
- 각 단계에서 사이클을 이루지 않는 최소 비용 간선 선택
  - "<u>최소 비용의 간선으로 구성, 사이클을 포함하지 않음</u>이라는 MST 조건에 근거
- 간선 중심 알고리즘 (간선 리스트 활용)
- 동작 과정
  1. 그래프의 간선들을 가중치의 오름차순으로 정렬
  2. 정렬된 간선 리스트에서 순서대로 사이클을 형성하지 않는 간선 선택
     - 가중치가 가장 낮은 것부터 선택 (사이클을 형성하는 간선은 제외)
     - Union-find 알고리즘 활용하여 사이클 유무 체크 (union 실패시 즉, 부모가 같을 시에 사이클 존재한다는 뜻)
  3. 해당 간선을 최소 비용 신장 트리 집합에 추가
- 시간 복잡도
  - 간선들을 정렬하는 시간에 좌우됨
    - 간선 e개를 퀵 정렬과 같은 효율적인 알고리즘으로 정렬한다면 O(elog₂e)
- 그래프의 간선이 적다면 (희소 그래프라면) Kruskal 알고리즘이 적합



### Prim 알고리즘

- 시작 정점에서부터 출발하여 신장트리 집합을 단계적으로 확장해나가는 방법

- 정점 중심 알고리즘 (인접 행렬, 인접 리스트 활용)

- 이전 단계에서 만들어진 신장 트리를 확장하는 방법

- 동작

  1. 처음에는 시작 정점만이 최소 비용 신장 트리 집합에 포함됨
     - 임의의 정점을 시작점으로 하여 시작
  2. 앞 단계에서 만들어진 MST 집합에 인접한 정점들 중에서 최소 간선으로 연결된 정점을 선택하여 트리 확장
     - 가중치 낮은 것부터 먼저 선택
  3. 위의 과정을 트리가 n-1개의 간선을 가질 때까지 반복

- 시간 복잡도

  - 주 반복문이 정점 수 N개 만큼 반복, 내부 반복문이 N번 반복
  - O(n^2)

- 각 정점의 가중치를 비교하기 때문에 정점의 수가 적을수록 유리함

  정점보다 간선의 수가 많은 밀집 그래프에서 유리함



### Kruskal vs. Prim

|                        Kruskal                        |                             Prim                             |
| :---------------------------------------------------: | :----------------------------------------------------------: |
|                       간선 위주                       |                          정점 위주                           |
| 시작점 정하지 않음 <br/>(최소 비용의 간선을 차례로..) |                시작점에서 가까운 정점을 선택                 |
|          간선 기준 정렬하는 과정이 오래걸림           | 최소 거리의 정점을 찾는 부분에서 <br/>자료구조의 성능 영향 받음 |
|              간선 개수가 작은 경우 사용               |                  간선 개수가 많은 경우 사용                  |









> 참고
>
> https://gmlwjd9405.github.io/2018/08/29/algorithm-kruskal-mst.html
>
> https://gmlwjd9405.github.io/2018/08/28/algorithm-mst.html
>
> https://velog.io/@agugu95/Prims-Algorithm%ED%94%84%EB%A6%BC-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98
>
> https://velog.io/@fldfls/%EC%B5%9C%EC%86%8C-%EC%8B%A0%EC%9E%A5-%ED%8A%B8%EB%A6%AC-MST-%ED%81%AC%EB%A3%A8%EC%8A%A4%EC%B9%BC-%ED%94%84%EB%A6%BC-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98