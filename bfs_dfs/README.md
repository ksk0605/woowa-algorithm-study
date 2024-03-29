# BFS / DFS

## 그래프의 표현 
프로그래밍에서는 그래프를 크게 2가지 방식으로 표현한다. 
> * 인접 행렬 (Adjacency Matrix) : 2차원 배열로 그래프와 연결 관계를 표현하는 방식
> * 인접 리스트 (Adjacency List) : 리스트로 그래프의 연결 관계를 표현하는 방식 


#### 인접 행렬
인접행렬은 2차원 배열에 각 노드가 연결된 형태를 기록하는 방식. 
![](../image/그래프%20예시.jpeg)
위와 같은 그래프가 있을 때 
```py 
INF = 999999999

graph = [
    [0,7,5]
    [7,0,INF]
    [5,INF,0]
]
```
위와 같은 코드로 구현할 수 있다. 위 같이 서로 연결되지 않은 노드는 의미가 없이 큰 숫자로 초기화하는 경우가 많다. 

#### 인접 리스트
인접 리스트는 linked list 라는 자료구조를 사용하여 구현한다. 단, 파이썬에서는 기본 list 자료형이 다양한 기능을 제공하므로 list를 활용하는 경우가 많다. 

```py
graph = [[] for _ in range(3)]

graph[0].append((1,7))
graph[0].append((2,5))

graph[1].append((0,7))

graph[2].append((0,5))

print(graph) # [[(1,7), (2,5)], [(0,7)], [(0,5)]]
```

인접 행렬은 빠르지만 많은 메모리를 사용한다는 장단점이, 반대로 인접 리스트는 느리지만 적은 메모리를 사용한다는 장단점이 있다. 

## Depth-First-Search
깊이 우선 탐색이라고 부르며 그래프에서 깊은 부분을 우선적으로 탐색하는 알고리즘. 
정점(vertex)와 간선(edge)으로 이루어진 그래프를 탐색하는 대표적인 두가지 알고리즘 중 하나이다. 
N개의 데이터에 대해 O(N)이 소요된다.

## Breadth-First-Search 
너비 우선 탐색이라고 부르며 가까운 노드부터 순서대로 탐색하는 알고리즘. DFS와는 달리 가장 가까운 정점부터 모두 방문 후에 다음 노드를 찾아 나가는 방식을 취한다. 마찬가지로 O(N) 시간이 수행되며 일반적으로는 DFS 보다 빠른 편이다. 
> 재귀 함수 방식의 DFS를 구현시 컴퓨터 시스템 동장 특성상 실제 프로그램의 수행시간이 느려질 수 있다. 따라서 스택 라이브러리를 이용해 시간 복잡도를 완화하는 테크닉이 필요할 때가 있다.

## 몇가지 팁
* 단순한 방문이라면 둘중 어느것도 상관없다! 
* 경로의 특징을 저장해야하는 문제 (ex. 지나는 경로의 데이터가 같으면 안된다는 제한 등)에서는 DFS를 사용한다. 
* 최단거리 문제는 BFS 문제를 사용하자. BFS는 가까운 곳 부터 한 칸씩 범위를 늘려가는 특징이 있기 때문이다. 
