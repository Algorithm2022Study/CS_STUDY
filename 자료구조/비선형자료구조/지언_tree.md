## Tree
![](https://velog.velcdn.com/images/jifrozen/post/9fefd111-7ecc-4cce-b7a8-6c6c5b7cf715/image.png)

- 트리(Tree)는 그래프의 일종으로 정점과 간선을 이용하여 데이터의 배치 형태를 추상화한 자료구조이다.
- 서로 다른 두 노드를 연결하는 길이 하나뿐인 그래프를 트리라고 부른다.
- 힙(Heap)을 구현하는 방법 중 하나가 트리이다.

### 트리를 구성하고 있는 구성요소들(용어)
Node (노드) : 트리를 구성하고 있는 각각의 요소를 의미한다.
Edge (간선) : 트리를 구성하기 위해 노드와 노드를 연결하는 선을 의미한다.
Root Node (루트 노드) : 트리 구조에서 최상위에 있는 노드를 의미한다.
Terminal Node ( = leaf Node, 단말 노드) : 하위에 다른 노드가 연결되어 있지 않은 노드를 의미한다.
Internal Node (내부노드, 비단말 노드) : 단말 노드를 제외한 모든 노드로 루트 노드를 포함한다.

## 트리(Tree)의 특징
- 트리 자료구조는 일반적으로 대상 정보의 각 항목들을 계층적으로 구조화할 때 사용하는 비선형 자료구조이다.

- 트리의 구조는 '데이터 저장'의 의미보다는 '저장된 데이터를 더 효과적으로 탐색'하기 위해서 사용된다.

- 리스트와 다르게 데이터가 단순히 나열되는 구조 X --> 트리는 부모(parent)와 자식(child)의 계층적인 관계로 표현된다.

- 트리는 사이클이 없다. (만약 사이클이 만들어진다면, 그것은 트리가 아니고 그래프다)

- 트리에서 루트노드를 제외한 모든 노드는 단 하나의 부모노드를 가진다.



## 트리 순회
트리를 순회하는 방식은 총 4가지![](https://velog.velcdn.com/images/jifrozen/post/885fd251-1166-4cb7-a3d1-3cb7e17323c4/image.png)


1. 전위 순회(pre-order)
각 루트(Root)를 순차적으로 먼저 방문하는 방식이다.

(Root → 왼쪽 자식 → 오른쪽 자식)

1 → 2 → 4 → 8 → 9 → 5 → 10 → 11 → 3 → 6 → 13 → 7 → 14


2. 중위 순회(in-order)
왼쪽 하위 트리를 방문 후 루트(Root)를 방문하는 방식이다.

(왼쪽 자식 → Root → 오른쪽 자식)

8 → 4 → 9 → 2 → 10 → 5 → 11 → 1 → 6 → 13 → 3 →14 → 7


3. 후위 순회(post-order)
왼쪽 하위 트리부터 하위를 모두 방문 후 루트(Root)를 방문하는 방식이다.

(왼쪽 자식 → 오른쪽 자식 → Root)

8 → 9 → 4 → 10 → 11 → 5 → 2 → 13 → 6 → 14 → 7 → 3 → 1


4. 레벨 순회(level-order)
루트(Root)부터 계층 별로 방문하는 방식이다.

1 → 2 → 3 → 4 → 5 → 6 → 7 → 8 → 9 → 10 → 11 → 13 → 14


## 이진트리(Binary Tree)
- 트리 자료구조는 여러 가지 유형이 있는데, 그중 가장 기본이 되는 트리는 이진 트리(Binary Tree) 구조이다.

- 이진 트리는 2개 이하의 자식노드를 가진다. (자식노드가 없거나 1개의 자식노드만 가지는 것도 가능!)

- 2개의 자식노드 중에서 왼쪽의 노드를 Left Node라고 하고, 오른쪽의 노드를 Right Node라고 한다.

- 트리에서는 각 층별로 숫자를 매겨서 이를 트리의 Level(레벨)이라고 한다. 레벨의 값은 0 부터 시작하고 따라서 루트 노드의 레벨은 0 이다. 그리고 트리의 최고 레벨을 가리켜 해당 트리의 height(높이)라고 한다.
### Full Binary Tree&&Complete Binary Tree&&Binary Search Tree
모든 레벨이 꽉 찬 이진 트리를 가리켜 포화 이진 트리라고 한다. 위에서 아래로, 왼쪽에서 오른쪽으로 순서대로 차곡차곡 채워진 이진 트리를 가리켜 완전 이진 트리라고 한다. 모든 노드가 0개 혹은 2개의 자식 노드만을 갖는 이진 트리를 가리켜 정 이진 트리라고 한다. 배열로 구성된 Binary Tree는 노드의 개수가 n 개이고 root가 0이 아닌 1에서 시작할 때, i 번째 노드에 대해서 parent(i) = i/2 , left_child(i) = 2i , right_child(i) = 2i + 1 의 index 값을 갖는다.

> 사향 이진 트리 (Skewed Binary Tree) : linked list처럼 한 줄로 연결되어 있는 형태의 이진 트리

## 이진 탐색 트리(Binary Search Tree)
이진탐색트리의 목적은?
이진탐색 + 연결리스트

이진탐색 : 탐색에 소요되는 시간복잡도는 O(logN), but 삽입,삭제가 불가능

연결리스트 : 삽입, 삭제의 시간복잡도는 O(1), but 탐색하는 시간복잡도가 O(N)

이 두가지를 합하여 장점을 모두 얻는 것이 '이진탐색트리'

즉, 효율적인 탐색 능력을 가지고, 자료의 삽입 삭제도 가능하게 만들자

![](https://velog.velcdn.com/images/jifrozen/post/3a994604-76ca-4b0e-8331-1807be70680b/image.png)

### 특징
- 각 노드의 자식이 2개 이하
- 각 노드의 왼쪽 자식은 부모보다 작고, 오른쪽 자식은 부모보다 큼
- 중복된 노드가 없어야 함

중복이 없어야 하는 이유는?

검색 목적 자료구조인데, 굳이 중복이 많은 경우에 트리를 사용하여 검색 속도를 느리게 할 필요가 없음. (트리에 삽입하는 것보다, 노드에 count 값을 가지게 하여 처리하는 것이 훨씬 효율적)

![](https://velog.velcdn.com/images/jifrozen/post/392af0a5-73bb-46a2-b707-e25873fb6674/image.gif)
원하는 값을 찾을 때까지 현재의 노드값보다 찾고자하는 값이 작으면 왼쪽으로 움직이고, 크면 오른쪽으로 움직인다. 이렇게 원하는 값을 더 빠르게 찾을 수 있게 된다.

- 이진 탐색 트리의 탐색 연산은 O(log n)의 시간 복잡도를 갖는다. (편향 트리인 경우 O(N))
-> 이를 해결하기 위해 개선된 트리 AVL Tree, RedBlack Tree


## AVL 트리
AVL 트리는 스스로 균형을 잡는 이진 탐색 트리이다.

트리의 높이가 h일때 이진탐색트리의 시간 복잡도는 O(h)이다.
한쪽으로 치우친 편향 이진트리가 되면 트리의 높이가 높아지기 때문에 이를 방지하고자 높이 균형을 유지하는 AVL트리를 사용한다.

### 특징
- 이진 탐색 트리의 속성을 가진다.
- 왼쪽, 오른쪽 서브 트리의 높이 차이가 최대 1이다.
- 어떤 시점에서 높이 차이가 1보다 커지면 회전을 통해 균형을 잡아 높이 차이를 줄인다.
- AVL 트리의 높이를 logN으로 유지하기 때문에 삽입, 검색, 삭제의 시간 복잡도는 O(logn)이다.

## RedBlack Tree
레드 블랙 트리도 스스로 균형을 잡는 이진 탐색 트리이다.
![](https://velog.velcdn.com/images/jifrozen/post/0fbdfda2-5390-4302-b60f-3e3b422902a0/image.png)

## 특징
-이진 탐색 트리의 속성을 가진다
- 모든 노드는 빨간색 혹은 검은색이다.
- 모든 리프 노드(NIL)들은 검은색이다. (NIL : null leaf, 자료를 갖지 않고 트리의 끝을 나타내는 노드)
- 빨간색 노드의 자식은 검은색이다.
   == No Double Red(빨간색 노드가 연속으로 나올 수 없다)
- 모든 리프 노드에서 Black Depth는 같다.
   == 리프노드에서 루트 노드까지 가는 경로에서 만나는 검은색 노드의 개수가 같다.

  이러한 조건을 맞추지 못하면 두가지 방법을 통해 해결한다.

  ### Restructuring && Recoloring
![](https://velog.velcdn.com/images/jifrozen/post/608dba57-d6ab-4b87-b0a2-39b1b2de5812/image.png)

z 노드를 삽입하면 v노드와 같은 빨간색으로 double red가 발생한다.
조건에 안맞음! -> Restructuring && Recoloring 두가지 방법 중 하나를 선택해야한다.
선택하는 기준은 부모의 형제(uncle) 노드 -> w가 빨간색이냐 검정색이냐이다.
> w가 검정 -> Restructing 빨강 -> Recoloring


- Restructuring
w노드를 제외하고 나머지 노드를 오름차순 정렬 ->
4 - 6 - 7 가운데 값 부모로 만들고 나머지 자식으로 만듦 ->
부모는 검정으로 자식은 빨강으로 -> w노드 추가![](https://velog.velcdn.com/images/jifrozen/post/819511fb-4e95-4c39-9bef-da02efe8c6df/image.png)
 Restructuring은 어떤 노드를 insertion한 뒤 일어나므로 총 수행시간은 O(logn)

 - Recoloring
 ![](https://velog.velcdn.com/images/jifrozen/post/1410401f-f69b-4c49-9851-e60fc597d020/image.png)
 z의 부모 노드와 (v) 형제노드 (w)를 검정으로 만듦 -> 부모의 부모를 red로 만듦
 예외
 1. 부모의 보무가 root 노드라면? 조건에 따라 무조건 루트노드는 검정이여야함
2. 4 위에 또 다른 노드가 red임 -> double red 발생
-> 또 Restructuring && Recoloring 해야함
insertion O(logn) -> recoloring O(1) = O(logN)

-> 레드블랙트리에 삽입(insertion)하는경우, Restructuring을 하든, Recoloring을 하든 O(logn)이 걸린다.

> 왜 red_black tree가 밸런스한지?
가장 짧은 경우와 가장 긴 경우를 생각하면 됨 ->
가장 짧을 경우 검은색으로만 이뤄질 경우
가장 길 경우 검-빨-검-빨
=둘이 가장 크게 차이 날때는 2배 => 밸런스하다~

## 트라이(Trie)
정수형에서 이진탐색트리를 이용하면 시간복잡도 O(logN)
하지만 문자열에서 적용했을 때, 문자열 최대 길이가 M이면 O(M*logN)이 된다.
트라이 활용하면 -> O(M)
문자열을 저장하고 효율적으로 탐색하기 위한 트리 형태의 자료구조이다.
![](https://velog.velcdn.com/images/jifrozen/post/486d4163-0457-4ffb-94f8-4870eaa64e72/image.png)

### 특징
- 문자열을 탐색할 때, 하나하나씩 전부 비교하면서 탐색을 하는 것보다 시간 복잡도 측면에서 훨씬 더 효율적이다.
- 우리가 검색할 때 볼 수 있느 자동완성 기능, 사전검색 등 문자열을 탐색하는데 특화되어 있는 자료구조
- 예를 들어 'Datastructure'라는 단어를 검색하기 위해서는 제일 먼저 'D'를 찾고, 다음에 'a', 't', ... 의 순서로 찾으면 된다.
- 각 노드에서 자식들에 대한 포인터들을 배열로 모두 저장하고 있다는 점에서 저장 공간의 크기가 크다는 단점도 있다. (메모리 측면에서 비효율적일 수 있음!)


 출처
 https://velog.io/@kimdukbae/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%ED%8A%B8%EB%A6%AC-Tree#%ED%8E%B8%ED%96%A5-%EC%9D%B4%EC%A7%84-%ED%8A%B8%EB%A6%AC-skewed-binary-tree
 https://gyoogle.dev/blog/computer-science/data-structure/Binary%20Search%20Tree.html
 https://github.com/JaeYeopHan/Interview_Question_for_Beginner/tree/master/DataStructure#graph
https://zeddios.tistory.com/237
https://yoongrammer.tistory.com/72#AVL_%ED%8A%B8%EB%A6%AC(Tree)_%EA%B0%9C%EB%85%90_%EB%B0%8F_%EA%B5%AC%ED%98%84
https://code-lab1.tistory.com/62
https://gyoogle.dev/blog/computer-science/data-structure/Trie.html
https://velog.io/@kimdukbae/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-%ED%8A%B8%EB%9D%BC%EC%9D%B4-Trie