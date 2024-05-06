# JAVA Collection Framework

![overview](./resource/java-collection-framework.drawio.svg)

## Collection

### List

#### ArrayList

- Overcomes the fixed size limitation of an array
- Uses an array underline and grows as the array fills up.
- `add` method to add the element
- `set` method to update an index value
- `get` method to get the index value

```java
import java.util.ArrayList;

List<String> arr = ArrayList<>();
arr.add("Ramesh");
```

#### LinkedList

#### Stack

- LIFO, last in, first out
- Java has `java.util.Stack` class as Stack implementation. Methods are synchronized, so could slow. So, we prefer `java.util.Deque` as Stack.

```java
import java.util.Stack;

Stack<String> animals = new Stack<>();
animals.push("Cat");
animals.push("Dog");

System.out.println(animals.peek()); // Dog
System.out.println(animals.pop()); // Dog
```

#### Vector

### Set

#### EnumSet

#### HashSet

#### LinkedHashSet

#### TreeSet

### Queue

FIFO: First In, First Out

#### ArrayDeque

- Uses arrays to implement the queue functionality.
- Can add and remove elements from start and end of the queue.
- `offer` method to add an element
- `poll` method to get the first element
- `offerFirst` method to add element at the beginning
- `offerLast` method to add element at the end
- `peekFirst`
- `peekLast`
- `pollFirst`
- `pollLast`

```java
import java.util.Queue;

Queue<Integer> queue= new ArrayDeque<>();
queue.offer(12);
queue.offer(24);
queue.offer(36);

System.out.println(queue.poll()); // 12
```

#### LinkedList

Similar example as `ArrayDeque` and `ArrayList`

#### PriorityQueue

Behaves the same as Queue but with priority.

```java
import java.util.PriorityQueue;

Queue<Integer> pQueue = new PriorityQueue<>(); // smaller has greatest priority
pQueue.offer(2);
pQueue.offer(-2);

System.out.println(pQueue.poll()); // -2
```

## Map

### HashMap

### TreeMap

### EnumMap

### LinkedHashMap

### WeakHashMap

## Iterator

### ListIterator
