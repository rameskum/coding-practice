# Built-in Sort with Custom Comparator

## Custom Sorting in Python

In Python, you can use `list.sort()` to sort the content of the list in-place and `sorted(list)` to return a new list containing the sorted list. Optionally, they can take 2 extra parameters, reverse and key to change the default sorting order.

`list.sort(reverse = True|False, key = comp_function)`

- `reverse` = True will sort the list in descending order
- `key` is a function that specifies the sorting order

```python
words = ["zebra", "fat", "apple", "lion", "ink"]
# sort words alphabetically
words.sort()    # words = ["apple", "fat", "ink", "lion", "zebra"]

nums = [40, 100, 1, 5, 25, 10]
# sort nums in ascending order
nums.sort()     # nums = [1, 5, 10, 25, 40, 100]
# sort nums in descending order
nums.sort(reverse=True)      # nums = [100, 40, 25, 10, 5, 1]

# task tuples (description, priority)
tasks = [
    ('Cook dinner', 5),
    ('Buy grocery', 3)
]

# sort tasks by priority in ascending order
sorted_tasks = sorted(tasks, key=lambda task: task[1])
# or use cmp_to_key
sorted_tasks = sorted(tasks, key=cmp_to_key(lambda t1, t2: t1[1] - t2[1]))
# sorted_tasks = [('Buy grocery', 3), ('Cook dinner', 5)]
```

## Custom Sorting in Java

In Java, you can use `Arrays.sort(array)` to sort an array or `Collections.sort(list)` to sort a Java List, such as an ArrayList. We can pass `Collections.reverseOrder()` as the second argument to the sorting function to reverse the default sorting order. If we want to sort elements in an order other than their natural ordering or to sort elements that do not implement the `Comparable` interface, we can write a custom `Comparator` to define our own sorting order.

```java
import java.util.Arrays;
import java.util.Collections;

String words[] = { "zebra", "fat", "apple", "lion", "ink" };
// sort words alphabetically
Arrays.sort(words);   // words = ["apple", "fat", "ink", "lion", "zebra"]

ArrayList<Integer> nums = new ArrayList<Integer>(
    Arrays.asList(40, 100, 1, 5, 25, 10));
// sort nums in ascending order
Collections.sort(nums);     // nums = [1, 5, 10, 25, 40, 100]
// sort nums in descending order
Collections.sort(nums, Collections.reverseOrder());     // nums = [100, 40, 25, 10, 5, 1]

public class Task {
    private String description;
    private int priority;

    // standard constructors, getters/setters, equals and hashcode
}

List<Task> tasks = Lists.newArrayList(
    new Task("Cook dinner", 5),
    new Task("Buy grocery", 3)
);
// sort tasks by priority in ascending order using Lambda support in Java 8
Collections.sort(tasks, (Task t1, Task t2) -> t1.getPriority().compareTo(t2.getPriority()));
// we can also separate out the comparator
Comparator<Task> comp = (Task t1, Task t2) -> {
    return t1.getPriority().compareTo(t2.getPriority());
};
Collections.sort(tasks, comp);
```
