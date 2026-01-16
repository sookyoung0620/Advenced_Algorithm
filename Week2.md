# Advanced Algorithmic — Week 2  
## Algorithm Analysis & Sorting

---

## Quick Recap (Week 1)

### Key Concepts
- Definition of an algorithm
- Importance of time complexity
- Asymptotic notations: Big O, Ω, Θ

### Practice Takeaways
- Growth rates: O(1), O(n), O(n²), O(2ⁿ), ...
- Comparison between Linear Search and Binary Search

---

## Refining Big O, Ω, and Θ

Asymptotic notations describe algorithm performance in different scenarios:

- **Big O (O)**: Worst-case time complexity
- **Big Omega (Ω)**: Best-case time complexity
- **Big Theta (Θ)**: Average-case (tight bound)

These notations help predict how an algorithm behaves as input size increases.

---

## Bubble Sort

### Basic Bubble Sort
- Repeatedly compares adjacent elements
- Swaps them if they are in the wrong order
- Largest elements “bubble up” to the end of the array

#### Time Complexity
- Worst-case: **O(n²)**
- Best-case: **O(n²)** (basic version)

---

### Optimized Bubble Sort

An optimized version of Bubble Sort improves efficiency by stopping early when no swaps occur during a full pass.

#### Key Idea
- A flag is used to detect whether any swap occurs
- If no swaps occur, the array is already sorted
- The algorithm terminates early to avoid unnecessary passes

#### Time Complexity
- Best-case: **O(n)** (already sorted array)
- Worst-case: **O(n²)**

---

## Benefits of Estimating Execution Time

- Identify inefficient approaches before implementation
- Predict performance based on input size
- Choose the most suitable algorithm for a given task
- Essential for large-scale systems (e.g., social media platforms)

---

## Analyzing Algorithm Performance

### Key Techniques
- Counting basic operations (comparisons, swaps)
- Worst-case vs. average-case analysis
- Impact of input size on performance

### Loop Structures
- Single loop → **O(n)**
- Nested loops → **O(n²)**
- Sequential loops → **O(n)**

---

## Recursive Function Analysis

### Fibonacci Example
A naive recursive Fibonacci implementation illustrates how recursion can lead to inefficient performance.

#### Analysis
- Each function call generates two additional recursive calls
- The number of calls grows exponentially
- Time Complexity: **O(2ⁿ)**

---

## Key Takeaways (Week 2)

- Big O, Ω, and Θ describe algorithm behavior under different conditions
- Bubble Sort is a classic example of a quadratic-time algorithm
- Simple optimizations can significantly improve best-case performance
- Recursive algorithms require careful complexity analysis


# Advanced Algorithmic — Week 2  
## 알고리즘 분석과 정렬

---

## 빠른 복습 (Week 1)

### 핵심 개념
- 알고리즘의 정의
- 시간 복잡도의 중요성
- 점근적 표기법: Big O, Ω, Θ

### 실습 요약
- 시간 복잡도 성장률: O(1), O(n), O(n²), O(2ⁿ) 등
- 선형 탐색과 이진 탐색 비교

---

## Big O, Ω, Θ의 심화 이해

점근적 표기법은 알고리즘의 성능을 서로 다른 상황에서 설명한다.

- **Big O (O)**: 최악의 경우 시간 복잡도
- **Big Omega (Ω)**: 최선의 경우 시간 복잡도
- **Big Theta (Θ)**: 평균적인 경우 또는 정확한 성장률

이 표기법들은 입력 크기가 증가할 때 알고리즘의 성능을 예측하는 데 사용된다.

---

## 버블 정렬 (Bubble Sort)
```python
def bubble_sort(arr):
    n - len(arr)
    for i in range(n):
        for j in range(0, n  - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
```

### 기본 버블 정렬
- 인접한 두 원소를 반복적으로 비교한다
- 순서가 잘못되었을 경우 교환한다
- 큰 값이 배열의 뒤쪽으로 이동하는 방식이다

#### 시간 복잡도
- 최악의 경우: **O(n²)**
- 최선의 경우: **O(n²)** (기본 버전)

---

### 최적화된 버블 정렬 (Optimized Bubble Sort)

최적화된 버블 정렬은 한 번의 반복 과정에서  
**교환이 발생하지 않으면 정렬이 완료된 것으로 판단하고 종료**한다.
```python
def bubble_sort_optimized(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
                swapped = True
        if not swapped:
            break
    return arr
```

#### 핵심 아이디어
- 교환 발생 여부를 확인하는 플래그를 사용한다
- 교환이 없을 경우 더 이상의 반복은 불필요하다
- 불필요한 비교를 줄여 성능을 개선한다

#### 시간 복잡도
- 최선의 경우: **O(n)** (이미 정렬된 배열)
- 최악의 경우: **O(n²)**

---

## 실행 시간 추정의 장점

- 비효율적인 알고리즘을 구현 전에 식별할 수 있다
- 입력 크기에 따른 성능을 사전에 예측할 수 있다
- 문제에 가장 적합한 알고리즘을 선택할 수 있다
- 대규모 시스템에서 효율적인 알고리즘은 필수적이다

---

## 알고리즘 성능 분석 방법

### 주요 분석 기법
- 기본 연산 수 세기 (비교, 교환 등)
- 최악 / 평균 경우 분석
- 입력 크기 증가에 따른 성능 변화 분석

### 반복문 구조 예시
- 단일 반복문 → **O(n)**
- 중첩 반복문 → **O(n²)**
- 순차 반복문 → **O(n)**

---

## 재귀 함수 분석

### 피보나치 수열 예시
단순 재귀 피보나치 함수는 재귀 호출의 비효율성을 잘 보여준다.

#### 분석
- 하나의 함수 호출이 두 개의 재귀 호출을 생성한다
- 호출 횟수가 지수적으로 증가한다
- 시간 복잡도: **O(2ⁿ)**

---

## 핵심 정리 (Week 2)

- Big O, Ω, Θ는 알고리즘의 실행 상황을 구분해 설명한다
- 버블 정렬은 이차 시간 복잡도의 대표적인 예시이다
- 간단한 최적화로 최선의 경우 성능을 크게 개선할 수 있다
- 재귀 알고리즘은 반드시 시간 복잡도 분석이 필요하다
