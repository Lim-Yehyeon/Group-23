## Link
[최소 스패닝 트리](https://www.acmicpc.net/problem/1197)

## Topic
- Minimum Spanning Tree (Kruskal / Prim) 

## Approach
 최소 스패닝 트리는 간선 / 정점 위주의 알고리즘에 따라 크루스칼 또는 프림 알고리즘을 사용할 수 있다.  
 크루스칼 알고리즘을 통해 최소 스패닝 트리를 구성하려면,

 1. 간선을 오름차 순으로 정렬한다.
 2. 간선을 차례로 꺼내어 Union-Find로 두 정점을 병합해본다.
    - 사이클이 존재하면 건너뛴다.
 3. 병합 후 다음 두 조건에 따라 알고리즘을 종료한다.
    - 성공: 병합 후 그래프의 정점 개수가 `|V|`개 일 때, 또는 간선의 개수가 `|V|-1`일 때
    - 실패: 모든 간선을 조사했음에도 정점 개수가 부족할 때

## Note
- 병합한 결과는 어떤 형태로 돌려줄까?  
  => 간선의 집합으로 돌려준다.
- **실수1**: Union-Find의 Find() 연산에서 탈출조건에 root 번호가 아닌 정점 번호로 비교하였다.
- **실수2**: 간선 순회 이전에 정렬하지 않았다.