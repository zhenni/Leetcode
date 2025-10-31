# Python Data Structure

## Data Structure

{% embed url="https://docs.python.org/3/tutorial/datastructures.html" %}

### HashMap

```python
dict()
collecitons.defaultdict() 
```

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

### Heap

```python
import heapq

# Creating an initial heap
h = [10, 20, 15, 30, 40]
heapq.heapify(h)

# Appending an element
heapq.heappush(h, 5)

# Heap before popping
print(h)

# Pop the smallest element from the heap
min = heapq.heappop(h)
print("Smallest:", min)
print(h)

class Point(object):
    def __init__(self, x, y):
        self.x, self.y = x, y
    
    def __lt__(self, other):
        return self.x*self.x+self.y*self.y < other.x*other.x+other.y*other.y

```

### Set

```python
basket = {'apple', 'orange', 'apple', 'pear', 'orange', 'banana'}
print(basket)                      # show that duplicates have been removed
{'orange', 'banana', 'pear', 'apple'}
'orange' in basket                 # fast membership testing
True
'crabgrass' in basket
False

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

#### Deque

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

