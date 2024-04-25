# Hash Map Intro

[link](https://algo.monster/problems/hashmap_intro)

`get_counter()` takes an integer array and returns a hash table with the array elements as keys and their frequencies as values.

```python
def get_counter(arr):
    counter = {}
    for num in arr:
        if num in counter:
            counter[num] += 1
        else:
            counter[num] = 1
    return counter

if __name__ == '__main__':
    arr = [int(x) for x in input().split()]
    res = get_counter(arr)
    for key in sorted(res.keys()):
        print(key, res[key])
```
