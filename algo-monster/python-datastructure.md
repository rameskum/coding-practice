# Python Data Structures

## Array

### Indexing

Negative indices are also allowed. A handy way to access the last element is by using the index -1:

```python
# accessing via index
a = [1, 2, 3]
print(a[-1]) # prints 3
```

### SubArray

Subarray slicing indices are left-inclusive and right-exclusive. For example,

```python
a = [0, 10, 20, 30, 40, 50]
subarray = a[2:5]  # element from index 2 to index 4 (cuz right exclusive, 5-1=4)
# subarray = [20, 30, 40]
subarray = a[:2]
# subarray = [0, 10]
subarray = a[2:]
# subarray = [20, 30, 40, 50] # skip first two elements
```

### Loop

```python
nums = [0, 10, 20, 30, 40, 50]
for i in nums:
    print(i)

# or use enumerate function to print the index

for i, num in enumerate(nums):
    print('i=', i, 'num=', num, 'num[i]=', nums[i])
```

## Linked List

There is no built-in implementation of a linked list. A general definition of a linked list node can be as follows:

```python
class LinkedListNode:
    def __init__(self, val, next=None):
        self.val = val
        self.next = next
```

## Stack

Python's `list` can be used as a stack. For a list `l = []`

- push: `append`, `O(1)`
- pop: `pop`, `O(1)`
- size: `len(l)`, `O(1)`
- top: `l[-1]`, `O(1)`

## Queue

Python's `collections.deque` is a double-ended queue. For a deque `q = deque()`

- enqueue: `q.append`, `O(1)`
- dequeue: `q.popleft()`, `O(1)`
- peek: `q[0]`, `O(1)`
- size: `len(q)`, `O(1)`

## Hash Table

Python's `dict` is an implementation of the hash table. For a dictionary `d = {}`

- get using a key: `d[key]`, `O(1)`, gives KeyError if key isn't in the dictionary
- set a key, value: `d[key] = value`, `O(1)`
- remove a key: `del d[key]`, `O(1)`
- size: `len(d)`, `O(1)`, returns the number of items in the dictionary.

Python `dict` has a convenient subclass `Counter` for counting hashable objects. When you pass an iterable object, such as a list or a string, to `Counter()`, it will return a new `dict` with elements as keys and their counts as values.

```python
from collections import Counter

word = "occur"
counter = Counter(word)
# counter = {'o': 1, 'c': 2, 'u': 1, 'r': 1}
print(counter['c'])    # prints out 2
print(counter['y'])    # prints out 0 for a non-existent element

# the number of unique elements in word can be obtained by the length of its counter
num_of_unique_elements = len(counter)
# num_of_unique_elements = 4
```

## Hash Set

Python's `set` is an implementation of hash set. It's useful in answering the existence queries in constant time. For a set `s = set()`,

- is `a` in set `s`: `a in s`, `O(1)`
- adding `a` to set: `s.add(a)`, `O(1)`. Duplicates will be discarded.
- removing `a` from set: `s.discard(a)`, `O(1)`. Does nothing if a is not in the set.

## Tree

Python does not have built-in tree support. Normally at an interview, you'd be given the following implementation for binary tree.

```python
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.left = None
        self.right = None
```

For n-nary trees:

```python
class TreeNode:
    def __init__(self, val):
        self.val = val
        self.children = []
```

## Priority Queue and Graph

To be covered later.

## Infinity

There are 2 ways to represent infinity as an integer in Python. The first one is to use float values:

```python
positive_inf = float('inf')
negative_inf = float('-inf')
```

Since Python 3.5, we can also use the `math` module.

```python
import math

positive_inf = math.inf
negative_inf = -math.inf
```
