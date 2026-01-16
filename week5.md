# Advanced Algorithmic — Week 5  
## Data Structures Overview & Algorithm Recap

---

## Big Recap (Weeks 1–4)

이번 주차는 지금까지 배운 알고리즘 개념을 정리하고  
**자료구조(Data Structures)**로 확장한다.

### Covered Topics
- Time Complexity
- Space Complexity
- Searching Algorithms
  - Linear Search
  - Binary Search
- Sorting Algorithms
  - Bubble Sort
  - Merge Sort
  - Insertion Sort

---

## What is a Data Structure?

### Definition
A **data structure** is an organized way to store, manage, and process data efficiently,  
enabling operations such as:
- Searching
- Insertion
- Deletion
- Traversal

### Why Data Structures Matter
- Enable efficient data storage and retrieval
- Help manage relationships between data
- Essential for designing efficient algorithms

---

## Classification of Data Structures

### 1. Linear Data Structures

Data elements are arranged sequentially.

#### Static
- **Array**

#### Dynamic
- **Stack**
- **Queue**
- **Linked List**

---

### 2. Non-Linear Data Structures

Data elements are organized hierarchically or graph-like.

- **Tree**
- **Graph**

---

## Arrays

### Characteristics
- Fixed-size collection of elements
- Stored in **contiguous memory**
- Direct access using index

### Time Complexity
- Access by index: **O(1)**

### Pros
- Simple structure
- Very fast lookups

### Cons
- Fixed size
- Resizing requires copying data

---

## Stack

### Concept
- **LIFO** (Last In, First Out)

### Core Operations
- Push: Add an element to the top
- Pop: Remove the top element
- Peek / Top: View the top element

### Use Cases
- Backtracking
- Undo operations
- Expression evaluation
- Function call stack

---

## Queue

### Concept
- **FIFO** (First In, First Out)

### Core Operations
- Enqueue: Add element to the back
- Dequeue: Remove element from the front
- Peek / Front: View the front element

### Use Cases
- Task scheduling
- Buffer management
- Breadth-First Search (BFS)

---

## Linked Lists

### Structure
Each node contains:
- **Data**: Stored value
- **Pointer**: Reference to the next node

### Types
- Singly Linked List
  - Each node points to the **next node only**
  - Can move in **one direction**
  - Uses **less memory** (one pointer per node)
  - [Data | Next] → [Data | Next] → [Data | Next] → None
- Doubly Linked List
  - Each node points to **both the previous and the next node**
  - Can move in **both directions**
  - Uses **more memory** (two pointers per node)
  - None ← [Prev | Data | Next] ↔ [Prev | Data | Next] ↔ [Prev | Data | Next] → None
- Circular Linked List
  - The **last node points back to the first node**
  - The list has **no end (no None)**
  - Can loop through the list continuously
  - [Data | Next] → [Data | Next] → [Data | Next]
          ↑__________________________________|
### Pros
- Dynamic size
- Efficient insertion and deletion

### Cons
- Sequential access only
- Lookup time: **O(n)**
- Extra memory for pointers

---

## Project (Group Work)

### Requirements
- Work in groups of two
- Choose a **real-world problem** that involves:
  - Searching
  - Sorting
  - Other operations (add, delete, reverse, etc.)

### Tasks
- Select the most suitable data structure
- Choose appropriate searching and sorting algorithms
- Justify your choices
- Be prepared to answer questions during presentation

---

## Key Takeaways (Week 5)

- Algorithms and data structures must be designed together
- Data structures directly affect algorithm efficiency
- Choosing the right structure simplifies algorithm design
- Real-world problems require trade-offs between time and space

# Advanced Algorithmic — Week 5  
## 자료구조 개요 및 알고리즘 복습

---

## 전체 복습 (Weeks 1–4)

이번 주차에서는 지금까지 학습한 알고리즘 개념을 정리하고,  
이를 **자료구조(Data Structures)** 개념으로 확장한다.

### 학습 내용
- 시간 복잡도 (Time Complexity)
- 공간 복잡도 (Space Complexity)
- 탐색 알고리즘
  - 선형 탐색 (Linear Search)
  - 이진 탐색 (Binary Search)
- 정렬 알고리즘
  - 버블 정렬 (Bubble Sort)
  - 병합 정렬 (Merge Sort)
  - 삽입 정렬 (Insertion Sort)

---

## 자료구조란 무엇인가?

### 정의
**자료구조(Data Structure)**란 데이터를 효율적으로 저장하고 관리하며 처리하기 위한 구조로,  
다음과 같은 연산을 가능하게 한다.
- 탐색 (Searching)
- 삽입 (Insertion)
- 삭제 (Deletion)
- 순회 (Traversal)

### 자료구조가 중요한 이유
- 데이터를 효율적으로 저장하고 빠르게 접근할 수 있게 해준다
- 데이터 간의 관계를 체계적으로 관리할 수 있다
- 효율적인 알고리즘 설계를 위해 필수적이다

---

## 자료구조의 분류

### 1. 선형 자료구조 (Linear Data Structures)

데이터가 **순차적으로 나열**된 구조이다.

#### 정적(Static)
- **배열 (Array)**

#### 동적(Dynamic)
- **스택 (Stack)**
- **큐 (Queue)**
- **연결 리스트 (Linked List)**

---

### 2. 비선형 자료구조 (Non-Linear Data Structures)

데이터가 **계층적 또는 그래프 형태**로 구성된다.

- **트리 (Tree)**
- **그래프 (Graph)**

---

## 배열 (Arrays)

### 특징
- 고정된 크기의 데이터 집합
- **연속된 메모리 공간**에 저장됨
- 인덱스를 통한 직접 접근 가능

### 시간 복잡도
- 인덱스 접근: **O(1)**

### 장점
- 구조가 단순함
- 매우 빠른 접근 속도

### 단점
- 크기가 고정됨
- 크기 변경 시 데이터 복사가 필요함

---

## 스택 (Stack)

### 개념
- **LIFO (Last In, First Out)**  
  마지막에 들어온 데이터가 먼저 나간다

### 주요 연산
- Push: 스택의 맨 위에 원소 추가
- Pop: 스택의 맨 위 원소 제거
- Peek / Top: 맨 위 원소 확인

### 활용 예
- 백트래킹
- 실행 취소(Undo) 기능
- 수식 계산
- 함수 호출 스택

---

## 큐 (Queue)

### 개념
- **FIFO (First In, First Out)**  
  먼저 들어온 데이터가 먼저 나간다

### 주요 연산
- Enqueue: 뒤쪽에 원소 추가
- Dequeue: 앞쪽에서 원소 제거
- Peek / Front: 맨 앞 원소 확인

### 활용 예
- 작업 스케줄링
- 버퍼 관리
- 너비 우선 탐색 (BFS)

---

## 연결 리스트 (Linked Lists)

### 구조
각 노드는 다음 두 요소를 포함한다.
- **데이터(Data)**: 저장된 값
- **포인터(Pointer)**: 다음 노드를 가리키는 참조

### 종류
- 단일 연결 리스트 (Singly Linked List)
- 이중 연결 리스트 (Doubly Linked List)
- 원형 연결 리스트 (Circular Linked List)

### 장점
- 동적 크기 조절 가능
- 삽입 및 삭제 연산이 효율적임

### 단점
- 순차 접근만 가능
- 탐색 시간: **O(n)**
- 포인터 저장을 위한 추가 메모리 필요

---

## 프로젝트 (팀 과제)

### 요구 사항
- 2인 1조로 진행
- 다음 연산을 포함하는 **현실 문제** 선택
  - 탐색
  - 정렬
  - 기타 연산 (추가, 삭제, 뒤집기 등)

### 수행 내용
- 가장 적합한 자료구조 선택
- 적절한 탐색 및 정렬 알고리즘 선택
- 선택 이유에 대한 근거 제시
- 발표 시 질의응답 준비

---

## 핵심 정리 (Week 5)








- 알고리즘과 자료구조는 함께 설계되어야 한다
- 자료구조 선택은 알고리즘의 효율성에 직접적인 영향을 미친다
- 올바른 자료구조 선택은 알고리즘 설계를 단순하게 만든다
- 실제 문제에서는 시간과 공간 사이의 절충이 필요하다
