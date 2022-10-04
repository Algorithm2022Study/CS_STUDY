# **Array**

## **배열이란?**

> 같은 타입의 여러 변수를 하나의 묶음으로 다루는 것
>

### **특징**

- 읽기 (장점)
    - 원소의 인덱스 값을 알고 있으면 O(1)에 해당 원소로 접근할 수 있다. (Random Access가 가능)

<aside>
💡 Random Access(비순차 접근) - 요소의 주소를 알고있다면 요소의 개수와 무관하게 쉽고 효율적으로 동일한 시간에 접근할 수 있는 방법 O(1)
Sequential access (순차 접근) - 순서대로 검색해서 접근하는 방법 O(n)

</aside>

- 탐색(단점)
    - 해당 value의 존재 유무와 위치를 모를 경우
    - 선형 검색(Linear Search) - 순서대로 0부터 끝까지 찾는 방법.

> 이진 검색 알고리즘배열의 단점 중 하나인 검색 시간을 단툭시키기 위한 검색법정렬된 배열에서만 사용이 가능하다.절반 검사하고 -> 절반 -> 절반
>
- 삽입 (단점)



  ![https://user-images.githubusercontent.com/50768959/161384455-ea7d1dfb-be37-4f08-96bf-87fb40f97e1d.jpg](https://user-images.githubusercontent.com/50768959/161384455-ea7d1dfb-be37-4f08-96bf-87fb40f97e1d.jpg)

- 삭제 (단점)

    ![https://user-images.githubusercontent.com/50768959/161384435-309bb86d-0b4e-4c13-a946-68ef389fb7fe.jpg](https://user-images.githubusercontent.com/50768959/161384435-309bb86d-0b4e-4c13-a946-68ef389fb7fe.jpg)

    - 특정 원소를 삽입 / 삭제 하기 위해서는, 해당 위치부터 1씩 shift를 실행한 뒤, 원소를 삽입 / 삭제해야 한다.
    - shift에는 O(n)이 걸리고 원소 삽입 / 삭제에는 O(1)이 걸리므로, 최종적으로 배열에서 최악의 삽입 시간 복잡도는 O(n)이 된다.

# **List**

- 순서가 의미를 갖는 데이터들의 집합이다.
- 삽입, 삭제, 검색 등의 기본적인 연산이 가능한 자료구조이다.
- 리스트를 구현하는 대표적인 두가지 방법은 ArrayList과 LinkedList이다.

> array와 list의 가장 큰 차이
array 메모리 공간에 할당할 사이즈를 미리 정해야함
List는 동적 할당으로 미리 사이즈 안정해도 됨
>

# **ArrayList**

### **특징**

- 읽기 (장점)
    - index를 가지고 있고 무작위 접근이 가능하기 때문에, 해당 index의 데이터를 한번에 가져올 수 있다.
    - 사이즈 동적 할당
- 삽입, 삭제 (단점)
    - 각 데이터 추가 / 삭제마다 배열을 새로 만들어 복사해주므로, 기존 10개에 데이터에 1개를 추가하면 10번의 복사가 요구되는 것이다. 따라서 O(n)의 시간복잡도가 추가/삭제에 요구된다.

> 어떻게 동적으로 사이즈 늘어나지?
>

```java
// ArrayList 클래스 코드
private Object[] grow(int minCapacity) {
        // 여기서 기존의 elementData(클라이언트는 arrayList를 사용한다면 이 배열을 사용할 것이다)를 newCapacity 길이만큼 새로 늘어난 배열에 카피한다.
        return this.elementData = Arrays.copyOf(this.elementData, this.newCapacity(minCapacity));
    }

// minCapacity는 일반적으로
// 기존 용량 + 기존 용량/2 (우측 시프트 연산) 측정한다
int newCapacity = oldCapacity + (oldCapacity >> 1);
```

# **LinkedList**

![](https://velog.velcdn.com/images/jifrozen/post/8b9c548a-4485-400f-a16c-2722797f5c32/image.png)


Array의 삭제, 삽입의 시간 복잡도 한계를 해결하기 위한 선형 자료구조이다.

노드들의 연결로 이루어져 있으며, 각 노드는 데이터 필드와 다음 노드에 대한 참조를 포함하고 있다.

## Singly Linked List (단일 연결 리스트)

### 데이터 삽입과 삭제

![](https://velog.velcdn.com/images/jifrozen/post/add1b764-91a1-4689-b5d8-91b7170a7b33/image.png)

![](https://velog.velcdn.com/images/jifrozen/post/cad20da5-52fe-4ddf-a707-4a5b13149053/image.png)


## doubly Linked list 이중 연결리스트
![](https://velog.velcdn.com/images/jifrozen/post/c3add939-e470-4b39-acef-371bfa17ad6f/image.png)


- LinkedList는 단방향이기 때문에 이전 요소 접근이 어엽다. 이를 보환한게 이중 연결리스트이다.
- 따라서, 단일 연결 리스트는 다음 노드에만 접근할 수 있지만, 이중 연결 리스트는 이전 노드와 다음 노드 모두에 접근할 수 있다.

```java
class Node{
	Node next;
	Node previous;
	Object obj;
}
```

### doubly circular linked list 이중원형 연결 리스트

![](https://velog.velcdn.com/images/jifrozen/post/16fd479e-a01a-430f-8153-922b5ca27e70/image.png)


마지막 요소의 다음요소가 첫번째 요소가 되고, 첫번째 요소의 이전 요소가 마지막 요소가 된다.

<aside>
💡 실제 LinkedList  클래스는 ‘더블 링크드 리스트’로 구현됨

</aside>

#### 연결리스트 비교
- 싱글 연결 리스트 : next 포인터만
- 이중 연결 리스트 : next 포인터와 prev 포인터
- 원형 이중 연결 리스트 : 이중 연결리스트와 같지만 마지막 노드의 next 포인터가 헤드 노드를 가리킨다.

## **특징**

- 동적 크기
    - Linked List는 배열과 다르게 길이가 정해져 있지 않다.
- Random Access 불가능
    - Linked List는 배열과 다르게 random access가 불가능하다.
    - 따라서 탐색을 위해서는 첫 번째 노드부터 순차적으로 원소에 접근해야 한다.
    - **이중 연결 리스트**의 경우에는 첫 번째 노드 또는 끝 노드 부터 순차적으로 접근하기 때문에, 탐색해야 하는 엘리먼트가 반으로 줄어든다.
    - 탐색시 시간복잡도 : O(n)
- 삽입, 삭제 용이
    - Linked List는 배열과 다르게 삽입,삭제시 shift가 필요 없다.
    - 원하는 위치 앞의 노드의 다음 노드 참조 값만 바꿔주면 된다.
    - 하지만 **단일 연결 리스트**의 경우, 삭제 또는 삽입할 위치 직전의 노드를 찾기 위해서는 탐색을 해야 하기 때문에, O(n)이다.
    - **이중 연결 리스트**의 경우, 삭제 또는 삽입할 위치의 노드의 참조를 현재 알고 있다면, O(1)이다.

## ArrayList vs LinkedList

탐색

배열 - 랜덤 접근 : 빠름
연결리스트 - 순차접근 : 느림

데이터 추가 밎 삭제

배열 - 전체를 옮겨야 추가/삭제 가능 : 느림
연결리스트 - 이전값과 다음값이 가르켰던 주소값만 수정하여 연결시켜주면 됨 : 빠름

따라서 상황에 맞게 자료구조를 선택해서 사용해야함

[https://zorba91.tistory.com/287](https://zorba91.tistory.com/287)

[https://dev-note-97.tistory.com/251](https://dev-note-97.tistory.com/251)

[https://github.com/prgrms-web-devcourse/BE-Team-R-CS-Study/blob/main/DataStructure_Algorithm](https://github.com/prgrms-web-devcourse/BE-Team-R-CS-Study/blob/main/DataStructure_Algorithm/2022-04-01-Array%26ArrayList%26LinkedList.md)