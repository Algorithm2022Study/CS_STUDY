# 그래프 탐색( DFS, BFS )

- 하나의 정점으로부터 시작하여 차례대로 모든 정점들을 한 번씩 방문

---

## 깊이 우선 탐색(DFS, Depth-First Search)

![](https://images.velog.io/images/jifrozen/post/09fccfac-cf29-4fa9-95b6-fb243cb1b784/Untitled.png)

임의의 노드에서 시작하여 최대한 깊숙이 들어가서 노트를 방문한 후,

다시 돌아가 다른 경로를 탐색하는 알리고리즘이다.

1. 시작 노드를 스택에 삽입 방문 처리
2. 스택의 최상단 노드에 방문 방문하지 않은 인접 노드가 있으면 그 인접 노트를 스택에 낳고 방문 처리를 한다.
3. 방문하지 않은 인접 노드가 없으면 스택에서 최상단 노드를 꺼낸다
4. 반복한다

```java
public class DFS {
	public static boolean[] visited=new boolean[9];
	public static ArrayList<ArrayList<Integer>> graph= new ArrayList<>();

	public static void dfs(int x){
		visited[x]=true;
		for(int i=0;i<graph.get(x).size();i++){
			int y=graph.get(x).get(i);
			if(!visited[y]) dfs(y);
		}
	}

	public static void main(String[] args){

		for(int i=0;i<9;i++){
			graph.add(new ArrayList<Integer>());
		}
		// 노드 1에 연결된 노드 정보 저장
		graph.get(1).add(2);
		graph.get(1).add(3);
		graph.get(1).add(8);

		// 노드 2에 연결된 노드 정보 저장
		graph.get(2).add(1);
		graph.get(2).add(7);

		// 노드 3에 연결된 노드 정보 저장
		graph.get(3).add(1);
		graph.get(3).add(4);
		graph.get(3).add(5);

		// 노드 4에 연결된 노드 정보 저장
		graph.get(4).add(3);
		graph.get(4).add(5);

		// 노드 5에 연결된 노드 정보 저장
		graph.get(5).add(3);
		graph.get(5).add(4);

		// 노드 6에 연결된 노드 정보 저장
		graph.get(6).add(7);

		// 노드 7에 연결된 노드 정보 저장
		graph.get(7).add(2);
		graph.get(7).add(6);
		graph.get(7).add(8);

		// 노드 8에 연결된 노드 정보 저장
		graph.get(8).add(1);
		graph.get(8).add(7);

		dfs(1);




	}
}
```

---

## 너비 우선 탐색 (BFS Breadth-First Search)

![](https://images.velog.io/images/jifrozen/post/4c161b4c-8660-47a4-a3f3-3b1bf9c220d6/Untitled%201.png)

임의의 노트를 선택해 인접한 노드를 먼저 탐색하는 알고리즘

- 사용하는 경우 : 두 노드 사이의 최단 경로 , 임의의 경로를 찾고 싶을 때
- 동작원리
1. 탐색 시작 노드를 큐에 삽입하고 방문처리
2. 큐에서 노드를 꺼내 해당 노드의 인접 노드 중에서 방문하지 않은 노드를 모두 큐에 삽입시킨다.
3. 반복한다

```
public class BFS {

	public static boolean[] visited=new boolean[9];
	public static ArrayList<ArrayList<Integer>> graph=new ArrayList<>();

	public static void bfs(int start){
		Queue<Integer> q=new LinkedList<>();
		q.offer(start);
		visited[start]=true;

		while(!q.isEmpty()) {
			int x = q.poll();
			for (int i = 0; i < graph.get(x).size(); i++) {
				int y = graph.get(x).get(i);
				if (!visited[y]) {
					q.offer(y);
					visited[y] = true;
				}
			}
		}
	}

	public static void main(String[] args){
		// 그래프 초기화
		for (int i = 0; i < 9; i++) {
			graph.add(new ArrayList<Integer>());
		}

		// 노드 1에 연결된 노드 정보 저장
		graph.get(1).add(2);
		graph.get(1).add(3);
		graph.get(1).add(8);

		// 노드 2에 연결된 노드 정보 저장
		graph.get(2).add(1);
		graph.get(2).add(7);

		// 노드 3에 연결된 노드 정보 저장
		graph.get(3).add(1);
		graph.get(3).add(4);
		graph.get(3).add(5);

		// 노드 4에 연결된 노드 정보 저장
		graph.get(4).add(3);
		graph.get(4).add(5);

		// 노드 5에 연결된 노드 정보 저장
		graph.get(5).add(3);
		graph.get(5).add(4);

		// 노드 6에 연결된 노드 정보 저장
		graph.get(6).add(7);

		// 노드 7에 연결된 노드 정보 저장
		graph.get(7).add(2);
		graph.get(7).add(6);
		graph.get(7).add(8);

		// 노드 8에 연결된 노드 정보 저장
		graph.get(8).add(1);
		graph.get(8).add(7);

		bfs(1);
	}
}

```