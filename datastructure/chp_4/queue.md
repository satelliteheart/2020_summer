# 큐 QUEUE

20200724

## 큐란?

**선입선출 (First-IN First-Out)** 뒤에서 새로운 데이터가 추가되고 앞에서 데이터가 하나씩 삭제되는 구조.
스택과 다른 점은 스택에서는 삽입과 삭제가 같은 쪽에서 일어나지만 큐는 다른 쪽에서 일어난다는 점

------------------------------
         전단(front)        후단(rear)
<-  @A@  <-  @B@  <-  &C&  <-  &D&  <-  @E@
\------------------------------ 
@@는 비어있고 &&는 차있는 것

### 큐의 추상 자료형

* 데이터 : 선입선출(FIFO)의 접근 방법을 유지하는 요소들의 모임
* 연산 :
    * enqueue(e) : 주어진 요소 e를 큐의 맨 뒤에 추가
    * dequeue() : 큐가 비어있지 않으면 맨 앞의 요소를 삭제하고 반환
    * isEmptu() : 큐가 비어 있으면 true 아니면 false
    * peek() : 큐가 비어있지 않으면 맨 앞 요소를 삭제하지 않고 반환
    * isFull() : 큐가 가득 차 있으면 true 아니면 false
    * size() : 큐의 모든 요소들의 개수를 반환
    * display() : 큐의 모든 요소를 출력

두개의 위치 변수가 필요하다.
1. rear : 삽입 관련
2. front : 삭제 관련


### 선형 큐

**시간 복잡도???**
계속 front와 rear은 증가하므로 항목 이동이 필요하다

### 원형 큐

원형 큐에서는 항상 칸 하나를 비워놔야 함. 포화 상태와 공백 상태를 구별하기 위함임.
`front == rear`이면 공백 상태

## 덱

**덱(deque : double-ended queue)** 는 큐의 전단과 후단에서 모두 삽입과 삭제가 가능한 큐. 하지만 중간에 삽입하거나 삭제는 허용하지 않는다.

### 덱의 추상 자료형

* 데이터 : 전단과 후단을 통한 접근을 허용하는 요소들의 모임
* 연산
    * addFront(e) : 주어진 요소 e를 덱의 맨 앞에 추가
    * deleteFront() : 덱이 비어있지 않다면 맨 앞의 요소를 삭제하고 반환
    * addRear(e)
    * deleteRear()
    * isEmpty()
    * getFront()
    * getRear()
    * isFull()
    * display() 

## 큐잉 이론

큐잉이론은 심화학습 때..

## 미로 탐색 프로그램

* 깊이 우선 탐색 [참고](https://gmlwjd9405.github.io/2018/08/14/algorithm-dfs.html)
    * 하나의 정점으로부터 시작하여 차례대로 모든 정점들을 한번씩 방문하는 것
    * 넓게 탐색하기 전에 깊게 탐색하는 것
    * 모든 노드를 방문하고자 하는 경우에
    * 너비 우선 탐색에 비해 간단하나 단순 검색 속도는 더 느림
    * 순환 알고리즘의 형태를 가지고 어떤 노드를 방문했었는지 여부를 반드시 검사해야한다.


* 너비 우선 탐색 [참고](https://gmlwjd9405.github.io/2018/08/15/algorithm-bfs.html)
    * 하나의 정점으로부터 시작하여 차례대로 모든 정점들을 한번씩 방문하는 것.
    * 루트 노드에서 시작해서 인접한 노드를 먼저 탐색하는 방법
    * 시작 정점으로부터 가까운 정점을 먼저 방문하고 멀리 떨어져 있는 정점을 나중에 방문하는 순회 방법
    * 깊게 탐색하기 전에 넓게 탐색하는 것
    * 두 노드 사이의 최단 경로 혹은 임의의 경로를 찾고 싶을 때
    * 깊이 탐색의 경우 모든 친구의 관계를 다 살펴봐야 할지도 모르지만 너비 탐색의 경우 가장 가까운 Ash의 관계부터 탐색한다
    * 이산구조 때 배운 Prim과 Dijkstra가 이와 비슷한 알고리즘