# Advanced Algorithmic — Week 4  
## Efficiency, Space Complexity, and In-place vs Out-of-place

---

## Quick Recap

이번 주차에서는 이전 주차에서 배운 내용을 바탕으로  
**알고리즘의 효율성(Efficiency)**을 더 넓은 관점에서 분석한다.

- Insertion Sort
- Merge Sort
- Space Complexity (공간 복잡도)

---

## What Does “Efficient Algorithm” Mean?

알고리즘의 효율성은 두 가지 관점에서 판단한다.

### 1. Time Efficiency (시간 효율성)
- 알고리즘이 얼마나 빠르게 실행되는가
- 입력 크기 증가에 따라 실행 시간이 어떻게 증가하는가

### 2. Space Efficiency (공간 효율성)
- 알고리즘이 **추가로 사용하는 메모리의 양**
- 시간만 빠르고 메모리를 과도하게 쓰는 알고리즘은 비효율적일 수 있음

---

## Space Complexity (공간 복잡도)

공간 복잡도는 입력 크기에 따라  
알고리즘이 필요로 하는 **추가 메모리 공간**을 의미한다.

### 공간 복잡도 계산 시 고려할 요소
- 입력 데이터 자체
- 사용되는 변수
- 함수 호출로 인한 메모리 사용
- **콜 스택(Call Stack)**
  - 재귀 호출
  - 함수 호출

---

## Recursive Function and Space Complexity

재귀 함수의 공간 복잡도는  
**재귀 호출로 인해 쌓이는 콜 스택의 깊이**에 의해 결정된다.

- 재귀 깊이가 `n`이면
- 공간 복잡도는 **O(n)**

👉 시간 복잡도와 공간 복잡도는 **서로 다를 수 있음**에 주의

---

## Insertion Sort — Time & Space Complexity

### 시간 복잡도
- Best case: **O(n)** (이미 정렬된 경우)
- Average case: **O(n²)**
- Worst case: **O(n²)** (역순 배열)

### 공간 복잡도
- 추가 배열을 사용하지 않는 **in-place 알고리즘**
- 공간 복잡도: **O(1)**

⚠️ 단, 함수 호출과 실행 환경에 따른 메모리 사용은 항상 고려해야 한다.

---

## Merge Sort — Time & Space Complexity

### 시간 복잡도
- Best / Average / Worst 모두 **O(n log n)**
- 입력 데이터 상태와 무관하게 안정적인 성능

### 공간 복잡도
- 병합 과정에서 **추가 배열 필요**
- 재귀 호출로 인한 콜 스택 사용

👉 공간 복잡도:
- **O(n)** (임시 배열)
- + **O(log n)** (재귀 호출 스택)

---

## In-place vs Out-of-place Algorithms

### In-place Algorithm
- 입력 데이터를 **직접 수정**
- 추가 메모리 사용이 거의 없음
- 공간 효율성이 좋음

**예시**
- Insertion Sort
- In-place 배열 뒤집기

### Out-of-place Algorithm
- 새로운 배열이나 추가 메모리를 사용
- 구현은 직관적이지만 메모리 비용이 큼

**예시**
- Merge Sort
- Out-of-place 배열 뒤집기

📌 큰 데이터셋을 다룰 때 out-of-place 알고리즘은 매우 무거울 수 있음

---

## Example: Reversing an Array

- In-place 방식: 두 포인터를 사용해 내부에서 교환
- Out-of-place 방식: 새로운 배열을 생성하여 복사

👉 결과는 같지만 **공간 복잡도는 완전히 다름**

---

## Exercises (Concept Summary)

### 1. Pair Sum Problem
- 배열 A에서 A[i] + A[j] = T 를 만족하는 쌍의 개수 세기
- 시간 복잡도와 공간 복잡도 분석 필수
```python
def count_pairs_sum_T(A, T):
    n = len(A)
    count = 0

    for i in range(n):
        for j in range(i + 1, n):
            if A[i] + A[j] == T:
                count += 1

    return count

```
시간 복잡도
- 바깥 루프: n
- 안쪽 루프: 평균 n/2, 최악 n
- Time: O(n²)

공간 복잡도
- 추가 자료구조 사용 없음
- Space: O(1)

### 2. Recursive Multiplication of Array
- 배열의 모든 원소를 재귀적으로 곱하기
- 재귀 깊이에 따른 공간 복잡도 분석
```python
def product_recursive(A, idx=0):
    if idx == len(A):
        return 1
    return A[idx] * product_recursive(A, idx + 1)
```
시간 복잡도
- 원소마다 곱셈 1번 → 총 n번
- Time: O(n)

공간 복잡도
- 재귀 호출 깊이 = n
- 콜 스택이 n만큼 쌓임
- Space: O(n)

### 3. Contiguous Subarray Sum
- 합이 T가 되는 연속 부분 배열 개수 세기
- 재귀 구조의 시간 / 공간 복잡도 분석
```python
def count_starting_at(A, T, i, j, current_sum):
    """
    Count how many contiguous subarrays starting at index i
    have sum == T, while extending the end index j.
    """
    # If j is beyond the array, stop
    if j == len(A):
        return 0

    # Extend the current subarray by including A[j]
    current_sum += A[j]

    # Count this subarray if its sum matches T
    count = 1 if current_sum == T else 0

    # Continue extending to the right
    return count + count_starting_at(A, T, i, j + 1, current_sum)


def count_subarrays(A, T, i=0):
    """
    Count how many contiguous subarrays in A have total sum == T.
    This checks all start indices i, and for each i, extends j to the right.
    """
    # If we passed the last start index, stop
    if i == len(A):
        return 0

    # Count subarrays starting at i
    count_here = count_starting_at(A, T, i, i, 0)

    # Move to next start index
    return count_here + count_subarrays(A, T, i + 1)

```
Time: O(n²)
Space: O(n) (재귀 콜스택 때문)

---

## Key Takeaways (Week 4)

- 알고리즘 효율성은 **시간 + 공간**을 함께 고려해야 한다
- 재귀 함수는 콜 스택으로 인해 공간 복잡도가 증가한다
- In-place 알고리즘은 공간 효율성이 뛰어나다
- Merge Sort는 빠르지만 메모리 비용이 크다
- Insertion Sort는 메모리는 적게 쓰지만 큰 입력에서는 느리다
