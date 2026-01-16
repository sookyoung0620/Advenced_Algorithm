# Advanced Algorithmic — Week 6  
## Data Structures Applications: Stack, Tree, Graph

---

## Quick Recap

Previously covered data structures:
- Array
- Stack
- Queue
- Linked List

This week focuses on **applying data structures** to solve practical problems.

---

## Parenthesis Checker (Stack)

### Problem
Given an expression containing characters `{ [ ( ) ] }`,  
determine whether the parentheses are **balanced**.

### Examples
- `{[(())]}` → True  
- `{[)}]` → False  
- `()[]` → True  

### Key Idea
- Use a **Stack**
- Push opening brackets
- Pop when a matching closing bracket appears
- Expression is balanced if the stack is empty at the end

---

## Duplicates Cleanup (Stack or Iteration)

### Problem
Given a paragraph (list of words),  
remove **adjacent duplicate words**.

### Example
Input:

### Key Idea
- Use a **Stack**
- Maintain elements in increasing order
- Pop elements that are greater than the current value

---

## Tree

### Definition
A **tree** is a hierarchical data structure consisting of nodes connected by edges.

### Terminology
- Root: Topmost node
- Leaf: Node with no children
- Each node has one parent (except root)

### Binary Tree
- Each node has at most **two children**
  - Left
  - Right

### Tree Traversals
- Inorder: Left → Root → Right
- Preorder: Root → Left → Right
- Postorder: Left → Right → Root

### Applications
- Hierarchical data storage
- Expression trees
- Decision trees

---

## Graph

### Definition
A **graph** is a collection of vertices (nodes) connected by edges.

### Types
- Directed Graph
- Undirected Graph
- Weighted Graph

### Representations
- Adjacency List
- Adjacency Matrix

### Traversal Algorithms
- Depth-First Search (DFS): explores deeply first
- Breadth-First Search (BFS): explores level by level

### Applications
- Social networks
- Shortest path problems
- Web crawling

---

## Project Guidelines

### Requirements
- Dataset with at least **5 elements**
- Operations to support:
  - Add an element
  - Delete an element by index
  - Update an element
  - Sort elements using at least **two attributes**
  - Filter elements based on one attribute
- No UI required (command-line only)

### Expectations
- Choose the most suitable data structure
- Select appropriate searching, sorting, and filtering algorithms
- Justify design choices during presentation

### Important Dates
- **Dec 19th**: Code review and Q&A
- **Jan 7th**: Final presentation


# Advanced Algorithmic — Week 6  
## 자료구조 응용: 스택, 트리, 그래프

---

## 빠른 복습

이전에 학습한 자료구조:
- 배열 (Array)
- 스택 (Stack)
- 큐 (Queue)
- 연결 리스트 (Linked List)

이번 주차에서는 **자료구조를 실제 문제에 적용**하는 데 초점을 둔다.

---

## 괄호 검사기 (Stack)

### 문제
`{ [ ( ) ] }` 문자로 이루어진 식이 주어졌을 때,  
괄호가 **올바르게 짝을 이루는지** 판단하라.

### 예시
- `{[(())]}` → True  
- `{[)}]` → False  
- `()[]` → True  

### 핵심 아이디어
- **스택(Stack)** 사용
- 여는 괄호는 push
- 닫는 괄호가 나오면 pop하여 짝이 맞는지 확인
- 모든 처리가 끝난 후 스택이 비어 있으면 균형 잡힘

---

## 중복 단어 제거 (Stack 또는 반복)

### 문제
문장에서 **연속으로 반복되는 단어**를 제거하라.

### 예시
입력:


### 핵심 아이디어
- **스택(Stack)** 사용
- 현재 값보다 큰 값은 스택에서 제거
- 스택의 top이 가장 가까운 작은 값

---

## 트리 (Tree)

### 정의
트리는 **계층적 구조**를 가지는 자료구조로,  
노드(Node)와 간선(Edge)으로 구성된다.

### 용어
- Root: 최상위 노드
- Leaf: 자식이 없는 노드
- 각 노드는 하나의 부모를 가짐 (루트 제외)

### 이진 트리 (Binary Tree)
- 각 노드는 최대 두 개의 자식 노드를 가짐
  - 왼쪽
  - 오른쪽

### 트리 순회
- 중위 순회 (Inorder): Left → Root → Right
- 전위 순회 (Preorder): Root → Left → Right
- 후위 순회 (Postorder): Left → Right → Root

### 활용
- 계층적 데이터 표현
- 수식 트리
- 의사결정 트리

---

## 그래프 (Graph)

### 정의
그래프는 **정점(Vertex)**과 이를 연결하는 **간선(Edge)**의 집합이다.

### 종류
- 방향 그래프 (Directed)
- 무방향 그래프 (Undirected)
- 가중 그래프 (Weighted)

### 표현 방식
- 인접 리스트 (Adjacency List)
- 인접 행렬 (Adjacency Matrix)

### 탐색 알고리즘
  

### 활용
- 소셜 네트워크
- 최단 경로 문제
- 웹 크롤링

---

## 프로젝트 안내

### 요구 사항
- 최소 **5개 요소**를 가진 데이터셋
- 다음 기능 구현:
  - 요소 추가
  - 인덱스 기반 삭제
  - 요소 수정
  - 최소 두 가지 속성 기준 정렬
  - 하나의 속성 기준 필터링
- UI 불필요 (커맨드라인 사용)

### 평가 포인트
- 문제에 적합한 자료구조 선택
- 적절한 정렬 및 탐색 알고리즘 사용
- 설계 선택에 대한 설명 가능해야 함

### 일정
- **12월 19일**: 코드 리뷰 및 질문
- **1월 7일**: 최종 발표
