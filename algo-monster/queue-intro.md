# Queue Intro

[link](https://algo.monster/problems/queue_intro)

```python
from collections import deque
from typing import List

def execute(program: List[str]) -> List[int]:
    queue = deque()
    for command in program:
        if command == "peek":
            if queue:
                print(queue[0])
            else:
                print("Queue is empty!")
        elif command == "pop":
            if queue:
                queue.popleft()
            else:
                print("Queue is empty!")
        else:
            data = int(command[5:])
            queue.append(data)
    return queue
```

Here is another problem that utilizes queue for you to practice on:

The function `rotate_left_till_zero()` takes an integer array containing one `0` and rotates the array counterclockwise so that the `0` ends up at the front of the array.

```python
from collections import deque

def rotate_left_till_zero(nums):
    queue = deque(nums)
    while queue[0] != 0:
        queue.append(queue.popleft())
    return queue

if __name__ == '__main__':
    nums = [int(x) for x in input().split()]
    res = rotate_left_till_zero(nums)
    print(' '.join(map(str, res)))
```
