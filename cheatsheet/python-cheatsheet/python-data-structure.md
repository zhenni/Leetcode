# Python Data Structure

## Data Structure

{% embed url="https://docs.python.org/3/tutorial/datastructures.html" %}

### Set

```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
## {'orange', 'banana', 'pear', 'apple'}
'orange' in basket                 # fast membership testing
## True
'crabgrass' in basket
## False
basket.add("pineapple")
## {'orange', 'banana', 'pear', 'apple', 'pineapple'}
basket.remove("orange")
## {'banana', 'pear', 'apple', 'pineapple'}

# Demonstrate set operations on unique letters from two words
a = set('abracadabra')
b = set('alacazam')
a                                  # unique letters in a
{'a', 'r', 'b', 'c', 'd'}
a - b                              # letters in a but not in b
{'r', 'd', 'b'}
a | b                              # letters in a or b or both
{'a', 'c', 'r', 'd', 'b', 'm', 'z', 'l'}
a & b                              # letters in both a and b
{'a', 'c'}
a ^ b                              # letters in a or b but not both
{'r', 'd', 'b', 'm', 'z', 'l'}
```

***

### HashMap

```python
dict()

del my_dict["age"]
removed_value = my_dict.pop("age")
 
from collections import defaultdict      # has initialization

my_defaultdict = defaultdict(int)
my_defaultdict['a'] += 1
my_defaultdict['b'] += 1
print(my_defaultdict)

my_list_defaultdict = defaultdict(list)
my_list_defaultdict['fruits'].append('apple')
my_list_defaultdict['fruits'].append('banana')
print(my_list_defaultdict)

from sortedcontainers import SortedDict
```

#### OrderedDict

hashmap + doubly-linked list

```
from collections import OrderedDict
d.move_to_end('a')                                # O(1) Move key 'a' to the end
d.move_to_end('b', last=False)                    # O(1) move to the front
d.popitem(last=True)                              # O(1) pop from the end
d.popitem(last=False)                             # O(1) pop from the front
```

***

### Stack

```python
def mono_stack(insert_entries):
    stack = []
    for entry in insert_entries:
        while stack and stack[-1] <= entry:
            stack.pop()
            # Do something with the popped item here
        stack.append(entry)
```

***

### Deque

```python
from collections import deque
d = deque('ghi')                 # make a new deque with three items
for elem in d:                   # iterate over the deque's elements
    print(elem.upper())

d.append('j')                    # add a new entry to the right side
d.appendleft('f')                # add a new entry to the left side
# deque(['f', 'g', 'h', 'i', 'j'])

d.pop()                          # return and remove the rightmost item
# 'j'
d.popleft()                      # return and remove the leftmost item
# 'f'
list(d)                          # list the contents of the deque
# ['g', 'h', 'i']

list(reversed(d))                # list the contents of a deque in reverse
# ['i', 'h', 'g']
'h' in d                         # search the deque
# True
d.extend('jkl')                  # add multiple elements at once
# deque(['g', 'h', 'i', 'j', 'k', 'l'])
d.rotate(1)                      # right rotation
# deque(['l', 'g', 'h', 'i', 'j', 'k'])
d.rotate(-1)                     # left rotation
# deque(['g', 'h', 'i', 'j', 'k', 'l'])

deque(reversed(d))               # make a new deque in reverse order
# deque(['l', 'k', 'j', 'i', 'h', 'g'])
d.clear()                        # empty the deque
d.pop()                          # cannot pop from an empty deque

d.extendleft('abc')              # extendleft() reverses the input order
# deque(['c', 'b', 'a'])
```

***

### Heap

```python
import heapq

h = [2, 3, 8]
heapq.heapify(h)                      # Creating an initial heap

heapq.heappush(h, 5)                  # Appending an element
# h: [2, 3, 5, 8]
min = heapq.heappop(h)                # Pop the smallest element from the heap
# min: 2, h: [3, 5, 8]
top = h[0]                            # Top: return the smallest element of the heap
# top: 3, h: [3, 5, 8]

min = heapq.heappushpop(h, 1)         # Push item, then pop smallest of old+new  
# min: 1, h: [3, 5, 8]                # heappush() + heappop()
min = heapq.heapreplace(h, 1)         # Pop smallest of old, insert new item.       
# min: 3, h: [1, 5, 8]                # heappop() + heappush()

heapq.nlargest(2, h)                  # return the largest k elements of the heap
# [8, 5], h: [1, 5, 8]                # nsmallest is the same way
```

#### Your own Comparison

1.  Use Tuple

    ```python
    # Example: sort by priority, then timestamp
    heapq.heappush(h, (priority, timestamp, value))
    ```
2.  Wrap objects and implement `__lt__`&#x20;

    ```python
    class Point(object):
        def __init__(self, x, y):
            self.x, self.y = x, y
        
        def __lt__(self, other):
            return self.x*self.x+self.y*self.y < other.x*other.x+other.y*other.y
    heapq.heappush(h, Point(1, 5))
    ```
3.  Use `functools.cmp_to_key` inside a wrapper object

    ```python
    from functools import cmp_to_key

    def my_compare(a, b):
        # example: reverse order (max heap)
        return b - a

    class Wrapper:
        def __init__(self, value):
            self.value = value
            self.key = cmp_to_key(my_compare)(value)

        def __lt__(self, other):
            return self.key < other.key

    h = []
    heapq.heappush(h, Wrapper(10))
    heapq.heappush(h, Wrapper(3))
    heapq.heappush(h, Wrapper(7))

    print(heapq.heappop(h).value)   # 10
    ```
