# Python Cheatsheet

## Type

### String

{% embed url="https://docs.python.org/3/library/string.html" %}

```python
my_string = "Hello World!"
lowercase_string = my_string.lower()

text3 = "123456"
print(f"'{text3}' is alphanumeric: {text3.isalnum()}")  # True
invalid_text1 = "Python 123"  # Contains a space
print(f"'{invalid_text1}' is alphanumeric: {invalid_text1.isalnum()}") # False
```

```python
string.ascii_letters
The concatenation of the ascii_lowercase and ascii_uppercase constants described below. This value is not locale-dependent.

string.ascii_lowercase
The lowercase letters 'abcdefghijklmnopqrstuvwxyz'. This value is not locale-dependent and will not change.

string.ascii_uppercase
The uppercase letters 'ABCDEFGHIJKLMNOPQRSTUVWXYZ'. This value is not locale-dependent and will not change.

string.digits
The string '0123456789'.

string.hexdigits
The string '0123456789abcdefABCDEF'.

string.octdigits
The string '01234567'.

string.punctuation
String of ASCII characters which are considered punctuation characters in the C locale: !"#$%&'()*+,-./:;<=>?@[\]^_`{|}~.

string.printable
String of ASCII characters which are considered printable by Python. This is a combination of digits, ascii_letters, punctuation, and whitespace.

Note By design, string.printable.isprintable() returns False. In particular, string.printable is not printable in the POSIX sense (see LC_CTYPE).
string.whitespace
A string containing all ASCII characters that are considered whitespace. This includes the characters space, tab, linefeed, return, formfeed, and vertical tab.
```

#### Format String

```python
"First, thou shalt count to {0}"  # References first positional argument
"Bring me a {}"                   # Implicitly references the first positional argument
"From {} to {}"                   # Same as "From {0} to {1}"
"My quest is {name}"              # References keyword argument 'name'
"Weight in tons {0.weight}"       # 'weight' attribute of first positional arg
"Units destroyed: {players[0]}"   # First element of keyword argument 'players'.
```

Aligning the text and specifying a width:

```python
'{:<30}'.format('left aligned')
'left aligned                  '
'{:>30}'.format('right aligned')
'                 right aligned'
'{:^30}'.format('centered')
'           centered           '
'{:*^30}'.format('centered')  # use '*' as a fill char
'***********centered***********'
```

Replacing `%+f`, `%-f`, and `% f` and specifying a sign:

```python
'{:+f}; {:+f}'.format(3.14, -3.14)  # show it always
'+3.140000; -3.140000'
'{: f}; {: f}'.format(3.14, -3.14)  # show a space for positive numbers
' 3.140000; -3.140000'
'{:-f}; {:-f}'.format(3.14, -3.14)  # show only the minus -- same as '{:f}; {:f}'
'3.140000; -3.140000'
```

Float

```python
value = 3.14159265 # Format to two decimal places
formatted_value = f"The value is: {value:.2f}"

signed_value = -12.345 # Format with a sign and two decimal places
formatted_signed = f"Signed value: {signed_value:+.2f}"

percentage_value = 0.75 # Format as a percentage
formatted_percentage = f"Percentage: {percentage_value:.2%}"

large_number = 1234567.89 # Format with thousands separator
formatted_large = f"Large number: {large_number:,.2f}"
```

Replacing `%x` and `%o` and converting the value to different bases:

```python
# format also supports binary numbers
"int: {0:d};  hex: {0:x};  oct: {0:o};  bin: {0:b}".format(42)
'int: 42;  hex: 2a;  oct: 52;  bin: 101010'
# with 0x, 0o, or 0b as prefix:
"int: {0:d};  hex: {0:#x};  oct: {0:#o};  bin: {0:#b}".format(42)
'int: 42;  hex: 0x2a;  oct: 0o52;  bin: 0b101010'
```

Using the comma or the underscore as a digit group separator:

```python
'{:,}'.format(1234567890)
'1,234,567,890'
'{:_}'.format(1234567890)
'1_234_567_890'
'{:_b}'.format(1234567890)
'100_1001_1001_0110_0000_0010_1101_0010'
'{:_x}'.format(1234567890)
'4996_02d2'
```

Expressing a percentage:

```python
points = 19
total = 22
'Correct answers: {:.2%}'.format(points/total)
'Correct answers: 86.36%'
```

Using type-specific formatting:

```python
import datetime
d = datetime.datetime(2010, 7, 4, 12, 15, 58)
'{:%Y-%m-%d %H:%M:%S}'.format(d)
'2010-07-04 12:15:58'
```

### Collections

{% embed url="https://docs.python.org/3/library/collections.html#collections.Counter" %}

```python
c = Counter()                           # a new, empty counter
c = Counter('gallahad')                 # a new counter from an iterable
c = Counter({'red': 4, 'blue': 2})      # a new counter from a mapping
c = Counter(cats=4, dogs=8)             # a new counter from keyword args

c = Counter(a=4, b=2, c=0, d=-2)
sorted(c.elements())                    # ['a', 'a', 'a', 'a', 'b', 'b']

for x, freq in c.items():               # iterate
```

***



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

## Algorithm

### Two Pointer (Opposite Direction)

```python
def two_pointers_opposite(arr):
    left, right = 0, len(arr) - 1
    while left < right:
        # Process current elements
        current = process(arr[left], arr[right])
        
        # Update pointers based on condition
        if condition(arr[left], arr[right]):
            left += 1
        else:
            right -= 1
```

### Same Direction

```python
def two_pointers_same(arr):
    slow, fast = 0, 0
    while fast < len(arr):
        # Process current elements
        current = process(arr[slow], arr[fast])
        
        # Update pointers based on condition
        if condition(arr[slow], arr[fast]):
            slow += 1
        
        # Fast pointer always moves forward
        fast += 1
```

### DFS in Graph

```python
def dfs(root, visited):
    for neighbor in get_neighbors(root):
        if neighbor in visited:
            continue
        visited.add(neighbor)
        dfs(neighbor, visited)
```

### DFS in Tree

```python
def dfs(root, target):
    if root is None:
        return None
    if root.val == target:
        return root
    left = dfs(root.left, target)
    if left is not None:
        return left
    return dfs(root.right, target)

```

### DFS Backtracing

```python
ans = []
def dfs(start_index, path, [...additional states]):
    if is_leaf(start_index):
        ans.append(path[:]) # add a copy of the path to the result
        return
    for edge in get_edges(start_index, [...additional states]):
        # prune if needed
        if not is_valid(edge):
            continue
        path.add(edge)
        if additional states:
            update(...additional states)
        dfs(start_index + len(edge), path, [...additional states])
        # revert(...additional states) if necessary e.g. permutations
        path.pop()

```

### DFS Backtracing Aggregation

```python
def dfs(start_index, [...additional states]):
    if is_leaf(start_index):
        return 1
    ans = initial_value
    for edge in get_edges(start_index, [...additional states]):
        if additional states: 
            update([...additional states])
        ans = aggregate(ans, dfs(start_index + len(edge), [...additional states]))
        if additional states: 
            revert([...additional states])
    return ans

```

### BFS on Graph

```python
def bfs(root):
    queue = deque([root])
    visited = set([root])
    while len(queue) > 0:
        node = queue.popleft()
        for neighbor in get_neighbors(node):
            if neighbor in visited:
                continue
            queue.append(neighbor)
            visited.add(neighbor)
```

### BFS on Tree

```python
def bfs(root):
    queue = deque([root])
    while len(queue) > 0:
        node = queue.popleft()
        for child in node.children:
            if is_goal(child):
                return FOUND(child)
            queue.append(child)
    return NOT_FOUND
```

### Prefix Tree

<pre class="language-python"><code class="lang-python"><strong>
</strong>class TrieNode:
    def __init__(self):
        self.children = {}
        self.isWord = False

# Build the trie
root = TrieNode()
for word in words:
    node = root
    for char in word:
        if char not in node.children:
            node.children[char] = TrieNode()
        node = node.children[char]
    node.isWord = True
</code></pre>

