# Union-Find란?
Union-Find의 개념
서로 중복되지 않는 부분 집합 (Disjoint Set = 서로소 집합 자료구조)을 표현할 때 사용하는 자료구조
초기화 / 합치기 (Union) / 찾기 (Find) 세 가지 연산을 사용한다
최소 스패닝 트리를 구현하는 크루스칼 알고리즘에 사용되며, 사이클을 만들지 않고 모든 노드를 방문할 수 있다
Union-Find의 구현
초기화 : N 개의 원소가 각각의 집합에 포함되어 있도록 초기화한다 -> 각각을 유일한 원소로 가지는 집합 생성
Union (합치기) : 두 원소 a, b 가 각각 속한 두 집합을 하나로 합친다 -> 두 개의 집합을 하나로 연결하는 역할
Find (찾기) : 원소 a 가 주어질 때, 이 원소가 속한 집합을 루트노드를 반환한다 -> a가 어느 집합에 속해있는지 찾는 역할 

![](https://blog.kakaocdn.net/dn/Wu6ip/btrPvi51AyZ/nwD9CCiKFkUrjksvOKmMKK/img.png)



# 두 포인터란?
두 포인터 (two-pointer)
: Two Pointers 는 1차원 배열에서 두 개의 포인터를 조작하여 원하는 결과를 얻는 알고리즘
리스트에 순차적으로 접근해야 할 때 두 개의 점의 위치를 기록하면서 처리
정렬되어있는 두 리스트의 합집합에도 사용됨.
* 두 개의 포인터를 사용하여 기존의 방식보다 시간을 개선할 수 있다.

![](https://blog.kakaocdn.net/dn/XGykr/btrPzaebQrg/8OylzmvpeWPRPmX0k0XC10/img.png)


# KMP 알고리즘이란?
KMP 알고리즘(문자열 처리 알고리즘)
: 특정 문자열에서 부분 문자열을 찾을 때 사용한다.
> KMP 알고리즘의 핵심은 이전까지 비교했던 정보를 기억하는 것 
> 접두사와 접미사를 활용해서 일정 부분이 맞는다면 Jump 하는 방식
- KMP 알고리즘은 부분문자열을 찾는 알고리즘 중 유일하게 선형 시간복잡도를 가지기때문에 유명하다. 



[ KMP의 기본 개념 ]

문자열 패턴 불일치가 발생한 전체 문자열에서 어떤 부분 문자열이 일치했는지 알고있다.
불일치가 발생한 앞 부분에 대하여 다시 비교하지 않고 매칭을 수행한다.

KMP 알고리즘 시간복잡도 : O(M+N) >> (N : 원본 문자열의 길이, M : 찾을 문자열의 길이)


![](https://blog.kakaocdn.net/dn/bhCnJV/btrPzjIPkrJ/P2sG8cxNFISQDhu06O5Ya0/img.png)

```
def simpleCompare(original, search) :
    for i in range(len(original)- len(search)) :
        flag = True
        for j in range(len(search)) :
            if original[i+j] != search[j] :
                flag = False
                break
        if flag :
            return i
    return -1

def makeFailureFunctionTable(word) :
    # j = 0, i = 1 부터 비교를 진행해 줍니다. ->KMP 알고리즘은 2글자 이상의 문자열에서만 적용됩니다.
    j = 0 
    table = [0]*len(word)   # 반환할 Table을 생성해줍니다.
    for i in range(1, len(word)) :
        while j > 0 and word[i] != word[j] :
            j = table[j-1] 
        if word[j] == word[i] :
            j += 1
            table[i] = j
    return table

def KMP(original, search) :
    table = makeFailureFunctionTable(search)
    j = 0
    for i in range(len(original)) :
        while j > 0 and search[j] != original[i] :
            j = table[j-1]
        if search[j] == original[i] :
            if j == len(search) -1 :
                print(i - len(search) + 1, "번째 인덱스에서부터 일치합니다.")
                j = table[j-1]
            j += 1

print(simpleCompare("abcdef", "cd"))
print(KMP("ababacabacaabacaaba", "abacaaba"))
```



