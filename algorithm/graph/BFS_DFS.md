## BFS(Breadth First Search)와 DFS(Depth First Search)

그래프를 공부해 보았다면 반드시 들어보았을 이름이다.  
BFS와 DFS의 목적은 같다: ``모든 정점을 1번씩 방문한다.``


하지만 이름에서 차이가 있듯, 둘은 분명히 차이점이 있다.  
하나씩 차근차근 알아보자.  

### DFS(깊이 우선 탐색)

DFS는 그래프를 최대한 깊숙하고 많이 가는 것을 깊이 우선 탐색이라고 한다.  


DFS는 스택을 사용해서 구현하며, 스택을 이용해서 갈 수 있는 만큼 최대한 많이 가고 갈 수 없으면 이전 정점으로 돌아가는 방식을 통해서 그래프를 탐색한다.  


스택을 사용한다는 것에서 눈치챘을 수 있지만, DFS는 재귀 호출을 이용해서 구현할 수 있다.  


구현은 다음 시간에...

### BFS(너비 우선 탐색)

그래프를 탐색 할 때, 최대한 넓게 가는 방법을 너비 우선 탐색이라고 한다.


그렇다면 ``넓게 간다``는 어떻게 구현해야 할까?  
큐를 이용해서 지금 위치에서 갈 수 있는 것을 모두 큐에 넣는 방식이라 할 수 있다. 큐에 넣을 때 방문했다고 체크해야 한다.  


구현은 다음 시간에...
### 시간 복잡도

두가지 그래프의 탐색방법은 모두 시간 복잡도가 같다.  
다만 인접 행렬 방식으로 구현된 그래프를 탐색했느냐, 인접 리스트 방식으로 구현된 그래프를 탐색했는지에 따른 시간 복잡도의 차이만 있을 뿐이다.

* 인접 행렬: O(V^2)
* 인접 리스트: O(V+E)
