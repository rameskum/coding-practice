# Stack Intro

[link](https://algo.monster/problems/stack_intro)

```python
from typing import List

def execute(program: List[str]) -> List[int]:
    stack = []
    for command in program:
        if command == "peek":
            print(stack[-1])
        elif command == "pop":
            stack.pop()
        else:
            data = int(command[5:])
            stack.append(data)
    return stack

if __name__ == '__main__':
    program = [input() for _ in range(int(input()))]
    res = execute(program)
    print(' '.join(map(str, res)))
```
