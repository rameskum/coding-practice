# Sorting Intro

## Insertion Sort

The idea of an insertion sort is this: initially, only the first item is considered sorted. Then, for each item in the sequence, we "insert" that item into the sorted list by swapping it with the item before it until the item is smaller than the current item.

> At any point in the loop, left hand side is sorted and right hand side is unsorted. As we navigate towards the right we insert the new element to its correct sorted position in the left hand side of the array.

- Stable Algorithm
- In Place

Overall complexity: `O(n * (n - 1) / 2)`, which is equivalent to `O(n^2)`.

```python
from typing import List

# O(n^2)
def sort_list(unsorted_list: List[int]) -> List[int]:
    for i, entry in enumerate(unsorted_list):
        current = i
        while current > 0 and unsorted_list[current] < unsorted_list[current - 1]:
            unsorted_list[current], unsorted_list[current - 1] = unsorted_list[current - 1], unsorted_list[current]
            current -= 1
    return unsorted_list

if __name__ == '__main__':
    unsorted_list = [2, 4, 5, 53, -2, 3, 2]
    print(sort_list(unsorted_list))
    # [-2, 2, 2, 3, 4, 5, 53]
```

## Selection Sort

The idea for this sorting algorithm is that during each cycle, we find the smallest item from the unsorted pile and add it to the sorted pile.
To find the smallest element in the unsorted pile, we have a temporary variable keeping track of the index to the smallest element. We then compare each element in the unsorted pile to that element, updating the new index if necessary.

> A each pass the correct element is selected for the current position.

- Not-Stable Algorithm
- In Place

```python
from typing import List

# O(n^2)
def sort_list(unsorted_list: List[int]) -> List[int]:
    n = len(unsorted_list)
    for i in range(n):
        min_idx = i
        for j in range(i + 1, n):
            if unsorted_list[j] < unsorted_list[min_idx]:
                min_idx = j
        unsorted_list[i], unsorted_list[min_idx] = unsorted_list[min_idx], unsorted_list[i]
    return unsorted_list

if __name__ == '__main__':
    unsorted_list = [2, 4, 5, 53, -2, 3, 2]
    print(sort_list(unsorted_list))
    # [-2, 2, 2, 3, 4, 5, 53]
```

## Bubble Sort

The idea of bubble sort is this: for each pass, we use a pointer to point at the first element of the list. For each cycle, we compare it to the next element in the list and swap them if the current item is greater, then move the pointer by one until it reaches the end of the list. We repeat this process until the list becomes sorted. The list is sorted if, during a pass, no swapping occurs.

- Stable
- In Place

```python
from typing import List

# O(n^2)
def sort_list(unsorted_list: List[int]) -> List[int]:
    n = len(unsorted_list)
    for i in reversed(range(n)):
        swapped = False
        for j in range(i):
            if unsorted_list[j] > unsorted_list[j + 1]:
                unsorted_list[j], unsorted_list[j + 1] = unsorted_list[j + 1], unsorted_list[j]
                swapped = True
        if not swapped:
            break
    return unsorted_list

if __name__ == '__main__':
    unsorted_list = [2, 4, 5, 53, -2, 3, 2]
    print(sort_list(unsorted_list))
    # [-2, 2, 2, 3, 4, 5, 53]
```
