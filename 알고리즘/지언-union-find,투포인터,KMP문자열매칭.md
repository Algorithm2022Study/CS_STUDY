# 유니온 파인드(Union-Find)
- 대표적 그래프 알고리즘으로 '합집합 찾기'라는 의미를 가지고 있다.
- 상호 배타적 집합(Disjoint-set)이라고도 한다.
- 여러 노드가 존재할 때, 두 개의 노드를 선택해서, 현재 두 노드가 서로 같은 그래프에 속하는지 판별하는 알고리즘
- 2가지 연산으로 이루어짐
	- find : x가 어떤 집합에 포함되어있는지 부모 찾기
    - Union : x와 y가 포함되어 있는 집합 합치기

  처음에는 모든 값이 자기 자신을 가리키토록 한다.
  ![](https://velog.velcdn.com/images/jifrozen/post/e7162ab1-fd10-45d7-9679-d76c09dd5569/image.png)
union(1,2) union(3,4) -> 부모를 합칠 때는 일반적으로 더 작은 값 쪽으로 합쳐진다.
![](https://velog.velcdn.com/images/jifrozen/post/78ee15e1-0bd1-4c9b-8c63-06a2433b9dc0/image.png)

```java
package 그래프_이론;

import java.util.*;

public class 기본_서로소 {

	public static int v,e;
	public static int[] parent=new int[10001];

	public static int findParent(int x){
		if(x==parent[x]) return x;
		return findParent(parent[x]);
		//return parent[x] = findParent(parent[x]);
	}

	public static void unionParent(int a,int b){
		a=findParent(a);
		b=findParent(b);
		if(a<b) parent[b]=a;
		else parent[a]=b;
	}

	public static void main(String[] args){
		Scanner sc=new Scanner(System.in);

		v=sc.nextInt();
		e=sc.nextInt();

		for(int i=1;i<=v;i++){
			parent[i]=i;
		}

		for(int i=0;i<e;i++){
			int a=sc.nextInt();
			int b=sc.nextInt();
			unionParent(a,b);
		}

		System.out.print("각 원소가 속한 집합: ");
		for(int i=1;i<=v;i++){
			System.out.print(findParent(i)+" ");
		}

		System.out.print("부모 테이블: ");
		for (int i = 1; i <= v; i++) {
			System.out.print(parent[i] + " ");
		}
	}


}

```

![](https://velog.velcdn.com/images/jifrozen/post/29d50acb-0b03-44d5-bedb-06f4ae09ccc0/image.png)


https://m.blog.naver.com/parkhj2416/221861837543

# 투포인터 알고리즘
투포인터 알고리즘은 말 그대로 start 와 end 두개의 포인터를 사용하여 답을 구하는 알고리즘이다.
- 포인터 2개를 준비한다. 시작과 끝을 알 수 있도록 start, end 라고 한다.
- 맨 처음에는 start = end = 0이며, 항상 start<=end을 만족해야 한다.
- 2개의 포인터는 현재 부분 배열의 시작과 끝을 가리키는 역할을 한다.

![](https://velog.velcdn.com/images/jifrozen/post/b17af29c-5b63-45a3-b615-a066fdd4e464/image.png)
배열 원소의 합이 5인 경우를 찾아보자.
원소의 합이 5보다 작다면 e를 이동시켜 원소를 더해준다.
만약 합이 5보다 크다면 s를 앞으로 이동시켜 원소를 빼준다.

투포인터 알고리즘은 슬라이딩 윈도우에도 활용된다.
둘은 비슷한 원리로 동작하지만 슬라이딩 윈도우는 일정 범위를 유지한다는 차이점이 존재한다.

매 루프마다 항상 두 포인터 중 하나는 1씩 증가하고 있고, 각 포인터가 N번 누적 증가해야 알고리즘이 끝난다. 따라서 각각 배열 끝에 다다르는데 O(N)이라서 합쳐도 O(N)이 된다.

https://github.com/WooVictory/Ready-For-Tech-Interview/blob/master/Algorithm/투포인터%20알고리즘.md

# KMP(Knuth-Morris_pratt) 알고리즘

KMP 알고리즘은 대표적인 문자열 매칭 알고리즘이다.
특정한 글이 있을 때 그 글 안에서 하나의 문자열을 찾는 알고리즘이다.
단순하게 이중 반목문을 통해 문자열을 찾을 수 있지만 시간복잡도가 굉장히 많이 늘어난다.
이를 방지하기 위해 모든 경우를 다 비교하지 않아도 부분 문자열을 찾을 수 있는 KMP알고리즘을 이용한다.

KMP 알고리즘은 접두사와 접미사의 개념을 활용하여, '반복되는 연산을 얼마나 줄일 수 있는지'를 판별하여 매칭할 문자열을 빠르게 점프하는 기법이다.
예를 들어 abacaaba 문자가 있다
여기서 KMP 알고리즘에서 필요한 접두사와 접미사는 이것이다. _aba_ca_aba_

접두사와 접미사가 일치하는 최대 길이가 필요하다.
![](https://velog.velcdn.com/images/jifrozen/post/45b095ea-3f83-4a39-a537-a57b45986d79/image.png)
위와 같이 접두사와 접미사를 구하게 되면 접두사와 접미사가 일치하는 경우 점프를 수행할 수 있어 매우 효율적이다.
```java
package 자료구조;

public class KMC알고리즘 {
	private static int[] makeTable(String pattern){
		int n=pattern.length();
		int[] table =new int[n];

		int index=0;

		for(int i=1;i<n;i++){
			while(index>0&&pattern.charAt(i)!=pattern.charAt(index)){
				index=table[index-1];
			}
			if (pattern.charAt(i) == pattern.charAt(index)) {
				index++;
				table[i]=index;
			}
		}
		return table;
	}
	public static void KMP(String parent,String pattern){
		int[] table=makeTable(pattern);

		int n1=parent.length();
		int n2=pattern.length();

		int index=0;
		for(int i=0;i<n1;i++){
			while(index>0&&parent.charAt(i)!=pattern.charAt(index)){
				index=table[index-1];
			}
			if(parent.charAt(i)==pattern.charAt(index)){
				if(index==n2-1){
					System.out.println(i-index+1+"번째 발견");
					index=table[index];
				}
				else{
					index++;
				}
			}
		}
	}
	public static void main(String[] args){
		String pattern="abacaaba";
		String parent="ababacabacaabacaaba";
		KMP(parent,pattern);
	}
}

```