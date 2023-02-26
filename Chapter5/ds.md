<br>

# Chapter 5. 자료 구조

## 0. 자료구조
: 효율적으로 데이터를 관리하고 수정, 삭제, 탐색, 저장할 수 있는 데이터셋
<br>

## 1. 복잡도
### 1.1 시간 복잡도
- 시간 복잡도 : 문제를 해결하는 데 걸리는 시간과 입력의 함수 관계, 실행 시간에 대한 효율성을 평가하는 척도
    
    #### Big-O Notation
    : 입력 범위 n을 기준으로 로직이 몇 번 반복되는지 가장 영향을 많이 끼치는 항, 즉 **최고차항의 지수**로만 나타냄 (계수, 나머지항 무시)

### 1.2 공간 복잡도
- 공간 복잡도 : 프로그램을 실행시켰을 때 필요로 하는 자원 공간의 양

### 1.3 자료 구조에서의 시간 복잡도
#### 평균 시간 복잡도
|자료 구조|접근|탐색|삽입|삭제|
|:---:|:---:|:---:|:---:|:---:|
|array|O(1)|O(n)|O(n)|O(n)|
|stack|O(n)|O(n)|O(1)|O(1)|
|queue|O(n)|O(n)|O(1)|O(1)|
|doubly linked list|O(n)|O(n)|O(1)|O(1)|
|hash table|O(1)|O(1)|O(1)|O(1)|
|BST|O(logn)|O(logn)|O(logn)|O(logn)|
|AVL tree|O(logn)|O(logn)|O(logn)|O(logn)|
|RB tree|O(logn)|O(logn)|O(logn)|O(logn)|

<br>

#### 최악 시간 복잡도
|자료 구조|접근|탐색|삽입|삭제|
|:---:|:---:|:---:|:---:|:---:|
|array|O(1)|O(n)|O(n)|O(n)|
|stack|O(n)|O(n)|O(1)|O(1)|
|queue|O(n)|O(n)|O(1)|O(1)|
|doubly linked list|O(n)|O(n)|O(1)|O(1)|
|**hash table**|O(n)|O(n)|O(n)|O(n)|
|**BST**|O(n)|O(n)|O(n)|O(n)|
|**AVL tree**|O(logn)|O(logn)|O(logn)|O(logn)|
|**RB tree**|O(logn)|O(logn)|O(logn)|O(logn)|

<br>

## 2. 선형 자료 구조
: 요소가 일렬로 나열되어 있는 자료 구조

### 2.1 연결 리스트 (Linked list)
- 연결 리스트 : 노드를 포인터로 연결
    
    - 싱글 연결 리스트 : next
    - 이중 연결 리스트 : next, prev
    - 원형 이중 연결 리스트 : next, prev + 마지막 노드의 next -> head

