# Advanced Algorithmic — Week 1  
## Algorithm & Time Complexity

---

## What is an Algorithm?

An **algorithm** is a step-by-step procedure used to solve a problem.

### Examples
- Cooking recipes
- Directions from one place to another
- Sorting or searching data in a program

### Key properties of an algorithm
- Correctness
- Efficiency
- Simplicity

---

## Why Time Complexity Matters

Time complexity describes how long an algorithm takes to run as the input size increases.

- Helps evaluate **algorithm efficiency**
- Crucial for **large-scale systems**
- Poor algorithm choices can cause severe performance issues
- Allows comparison between different approaches  
  (e.g., Linear Search vs Binary Search)

---

## Asymptotic Notations

Asymptotic notation is used to describe the growth rate of algorithms.

- **Big O (O)**: Upper bound (worst-case time complexity)
- **Big Omega (Ω)**: Lower bound (best-case time complexity)
- **Big Theta (Θ)**: Tight bound (exact growth rate)

---

## Common Time Complexity Classes

| Complexity | Description |
|-----------|------------|
| O(1) | Constant time |
| O(log n) | Logarithmic |
| O(n) | Linear |
| O(n log n) | Log-linear |
| O(n²) | Quadratic |
| O(2ⁿ) | Exponential |
| O(n!) | Factorial |

As `n` grows, algorithms with higher complexity become impractical.

---

## Algorithm Comparison Example

### Linear Search
- Checks elements one by one
- Time complexity: **O(n)**
```bash
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1
```

### Binary Search
- Requires sorted data
- Repeatedly halves the search space
- Time complexity: **O(log n)**

Binary search is significantly faster for large datasets.

```bash
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1
```

---

## Key Takeaways

- Algorithms define **how problems are solved**
- Performance is evaluated using **time complexity**
- Growth rate matters more than exact runtime
- Choosing the right algorithm is critical for efficiency

---

## Practice Tasks (Week 1)

### 1. Time Complexity Analysis
Determine the time complexity of given code snippets.

Examples:
- Nested loops → `O(n²)`
- Sequential loops → `O(n)`

### 2. Linear Search vs Binary Search
- Implement both algorithms
- Measure execution time on large inputs
- Compare performance and analyze results

# Advanced Algorithmic — Week 1  
## 알고리즘과 시간 복잡도 (Algorithm & Time Complexity)

---

## 알고리즘이란?

**알고리즘(Algorithm)**이란 문제를 해결하기 위한 단계별 절차를 의미한다.

### 예시
- 요리 레시피
- 한 장소에서 다른 장소로 가는 길 안내
- 프로그램에서 데이터를 정렬하거나 탐색하는 과정

### 알고리즘의 주요 특성
- 정확성 (Correctness)
- 효율성 (Efficiency)
- 단순성 (Simplicity)

---

## 시간 복잡도가 중요한 이유

시간 복잡도(Time Complexity)는 입력 크기가 증가함에 따라  
알고리즘의 실행 시간이 어떻게 변하는지를 설명한다.

- 알고리즘의 **성능 평가**에 사용됨
- **대규모 시스템**에서 매우 중요함
- 잘못된 알고리즘 선택은 심각한 성능 저하를 초래할 수 있음
- 서로 다른 알고리즘을 비교할 수 있는 기준 제공  
  (예: 선형 탐색 vs 이진 탐색)

---

## 점근적 표기법 (Asymptotic Notations)

점근적 표기법은 입력 크기가 커질 때 알고리즘의 **성장률**을 표현한다.

- **Big O (O)**: 최악의 경우 시간 복잡도 (상한)
- **Big Omega (Ω)**: 최선의 경우 시간 복잡도 (하한)
- **Big Theta (Θ)**: 정확한 성장률 (상한과 하한이 동일)

---

## 주요 시간 복잡도 종류

| 복잡도 | 설명 |
|------|------|
| O(1) | 상수 시간 |
| O(log n) | 로그 시간 |
| O(n) | 선형 시간 |
| O(n log n) | 로그-선형 시간 |
| O(n²) | 이차 시간 |
| O(2ⁿ) | 지수 시간 |
| O(n!) | 팩토리얼 시간 |

입력 크기 `n`이 증가할수록  
복잡도가 높은 알고리즘은 실용적이지 않다.

---

## 알고리즘 비교 예시

### 선형 탐색 (Linear Search)
- 배열의 요소를 처음부터 하나씩 검사
- 시간 복잡도: **O(n)**

```python
def linear_search(arr, target):
    for i in range(len(arr)):
        if arr[i] == target:
            return i
    return -1
```
### 이진 탐색 (Binary Search)
- 정렬된 배열이 필요
- 탐색 범위를 반복적으로 절반씩 줄임
- 시간 복잡도: O(log n)
- 대규모 데이터에서 선형 탐색보다 훨씬 빠르다.
```bash
def binary_search(arr, target):
    left = 0
    right = len(arr) - 1

    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1

    return -1
```

---
## 핵심 정리 (Key Takeaways)
- 알고리즘은 문제를 해결하는 방법을 정의한다
- 성능은 시간 복잡도로 평가한다
- 실제 실행 시간보다 성장률이 더 중요하다
- 효율적인 알고리즘 선택이 시스템 성능에 큰 영향을 미친다


