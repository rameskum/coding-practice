# Advanced Sorting Algorithms - Merge Sort | Quick Sort

## Merge Sort

### Take Away

In merge-sort, understand the merge algorithm to merge two sorted arrays. Learn both in-place and out-place algorithms.

```python
from typing import List

def sort_list(arr: List[int]) -> List[int]:
    n = len(arr)
    if(n == 1):
        return arr

    mid = n // 2

    left = sort_list(arr[:mid])
    right = sort_list(arr[mid:])

    # outplace merge, creating a new array
    result = []

    l = 0
    r = 0

    while (l < len(left) and r < len(right)):
        if left[l] < right[r]:
            result.append(left[l])
            l += 1
        else:
            result.append(right[r])
            r += 1

    while (l < len(left)):
        result.append(left[l])
        l += 1

    while (r < len(right)):
        result.append(right[r])
        r += 1

    return result

if __name__ == '__main__':
    unsorted_list = [2, 4, 5, 53, -2, 3, 2]
    print(sort_list(unsorted_list))
```

## Quick Sort

- **Worst Case**: If the array is already sorted `O(n^2)`.
- **Best Case**: If we always choose the median as pivot `O(n log(n))`.
- **Average Case**: It's difficult to compute the average case, but its `O(n log(n))`

### Take Away

Understand the partition algorithm to partition the array such that all elements on the left side of the pivot element are less than the pivot and all elements on the right-hand side of the pivot are greater than the pivot element, or in short, find the correct place of the pivot element.

```python
from typing import List

# choosing pivot at the end of the array
def partition(arr: List[int], l: int, r: int) -> int:
    pivot = arr[r]
    i = l - 1
    for j in range(l, r):
        if arr[j] < pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i + 1], arr[r] = arr[r], arr[i + 1]
    return i + 1

def qs(arr: List[int], l: int, r: int) -> None:
    if (l >= r):
        return
    p = partition(arr, l, r)
    qs(arr, l, p - 1)
    qs(arr, p + 1, r)

def sort_list(unsorted_list: List[int]) -> List[int]:
    qs(unsorted_list, 0, len(unsorted_list) - 1)
    return unsorted_list

if __name__ == '__main__':
    unsorted_list = [2, 4, 5, 53, -2, 3, 2]
    print(sort_list(unsorted_list))
```
