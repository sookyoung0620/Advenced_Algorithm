# Advanced Algorithmic — Week 3  
## Divide & Conquer and Space Complexity

---

## Quick Recap (Week 2)

- Asymptotic notations: Big O, Ω, Θ
- Bubble Sort and Optimized Bubble Sort
- Benefits of estimating execution time

---

## Merge Sort

Merge Sort is a **divide-and-conquer** sorting algorithm.

### How It Works
- Divide the array into two halves
- Recursively sort each half
- Merge the sorted halves into one sorted array

### Time Complexity
- Worst-case: **O(n log n)**
- Best-case: **O(n log n)**
- Average-case: **O(n log n)**

Merge Sort guarantees good performance regardless of input order.

```python
def merge(arr, left_half, right_half):
    i = j = k = 0

    # Merge the two halves
    while i < len(left_half) and j < len(right_half):
        if left_half[i] < right_half[j]:
            arr[k] = left_half[i]
            i += 1
        else:
            arr[k] = right_half[j]
            j += 1
        k += 1

    # Copy remaining elements of left_half
    while i < len(left_half):
        arr[k] = left_half[i]
        i += 1
        k += 1

    # Copy remaining elements of right_half
    while j < len(right_half):
        arr[k] = right_half[j]
        j += 1
        k += 1


def merge_sort(arr):
    if len(arr) <= 1:
        return

    mid = len(arr) // 2
    left_half = arr[:mid]
    right_half = arr[mid:]

    merge_sort(left_half)
    merge_sort(right_half)

    merge(arr, left_half, right_half)

```

---

## Insertion Sort

Insertion Sort builds the final sorted array one element at a time.

### How It Works
- Takes one element at a time
- Inserts it into the correct position among already sorted elements
- Similar to sorting playing cards in hand

### Time Complexity
- Worst-case: **O(n²)** (reverse sorted array)
- Best-case: **O(n)** (already sorted array)
- Average-case: **O(n²)**

Insertion Sort performs well on small or nearly sorted datasets.

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1

        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1

        arr[j + 1] = key

    return arr

```

---

## Space Complexity

Space complexity measures the **extra memory** required by an algorithm as input size grows.

### What Matters
- Variables used by the algorithm
- Memory used by function calls
- Call stack usage (especially in recursion)
- Additional data structures

---

## Space Complexity of Insertion Sort

- In-place algorithm
- Uses only a constant amount of extra memory
- Space Complexity: **O(1)**

⚠️ Always consider function calls when analyzing space usage.

---

## Space Complexity of Merge Sort

- Requires additional arrays to store subarrays
- Uses recursion (call stack)

### Space Complexity
- **O(n)** due to temporary arrays
- Additional **O(log n)** for recursive call stack

---

## Key Takeaways (Week 3)

- Merge Sort is efficient and stable with O(n log n) time complexity
- Insertion Sort is simple and efficient for small or nearly sorted inputs
- Space complexity is as important as time complexity
- Recursive algorithms require careful memory analysis


# Advanced Algorithmic — Week 3  
## 분할 정복과 공간 복잡도

---

## 빠른 복습 (Week 2)

- 점근적 표기법: Big O, Ω, Θ
- 버블 정렬과 최적화된 버블 정렬
- 실행 시간 추정의 중요성

---

## 병합 정렬 (Merge Sort)

병합 정렬은 **분할 정복(Divide and Conquer)** 방식의 정렬 알고리즘이다.

### 동작 방식
- 배열을 두 개의 부분 배열로 분할
- 각 부분 배열을 재귀적으로 정렬
- 정렬된 두 배열을 하나로 병합

### 시간 복잡도
- 최악의 경우: **O(n log n)**
- 최선의 경우: **O(n log n)**
- 평균적인 경우: **O(n log n)**

입력 데이터의 순서와 관계없이 일정한 성능을 보장한다.

---

## 삽입 정렬 (Insertion Sort)

삽입 정렬은 정렬된 부분 배열에  
새로운 원소를 하나씩 올바른 위치에 삽입하는 방식이다.

### 동작 방식
- 한 번에 하나의 원소를 선택
- 이미 정렬된 부분과 비교하여 적절한 위치에 삽입
- 카드 정렬 방식과 유사함

### 시간 복잡도
- 최악의 경우: **O(n²)** (역순 배열)
- 최선의 경우: **O(n)** (이미 정렬된 경우)
- 평균적인 경우: **O(n²)**

소규모 데이터나 거의 정렬된 데이터
