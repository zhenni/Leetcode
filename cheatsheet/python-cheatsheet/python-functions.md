# Python Functions

### Sort

```python
alist.sort(key=lambda x: x.foo)

# Sort by multiple attributes (age then name)
sorted_by_multiple = sorted(people, key=lambda p: (p.age, p.name))
print(f"Sorted by age then name: {sorted_by_multiple}")

from functools import cmp_to_key
sorted(mylist, key=cmp_to_key(lambda item1, item2: fitness(item1) - fitness(item2)))
```

### Binary Search

```python
import bisect

sorted_list = [1, 3, 5, 7, 9]

# Find insertion point for 5 (leftmost)
index_left = bisect.bisect_left(sorted_list, 5)
# >> 2

# Find insertion point for 5 (rightmost)
index_right = bisect.bisect_right(sorted_list, 5)
# >> 3

# Insert 4 while maintaining sorted order
bisect.insort_left(sorted_list, 4)
# >> [1, 3, 4, 5, 7, 9]

# Insert 6 while maintaining sorted order
bisect.insort_right(sorted_list, 6)
# >> [1, 3, 4, 5, 6, 7, 9]
```

***

### Itertools

{% embed url="https://docs.python.org/3/library/itertools.html" %}

<table data-header-hidden><thead><tr><th width="134.4609375"></th><th width="88.84375"></th><th width="206.76171875"></th><th></th></tr></thead><tbody><tr><td>​<a href="https://docs.python.org/3/library/itertools.html#itertools.zip_longest"><code>zip_longest()</code></a>​</td><td>p, q, …</td><td>(p[0], q[0]), (p[1], q[1]), …</td><td><code>zip_longest('ABCD', 'xy',fillvalue='-') → Ax By C- D-</code></td></tr><tr><td>​<a href="https://docs.python.org/3/library/itertools.html#itertools.accumulate"><code>accumulate()</code></a>​</td><td>p [,func]</td><td>p0, p0+p1, p0+p1+p2, …</td><td><code>accumulate([1,2,3,4,5]) → 1 3 6 10 15</code></td></tr></tbody></table>

```python
# python built-in:
a = [1, 2, 3]
b = ['a', 'b']

list(zip(a, b))
# [(1, 'a'), (2, 'b')]

itertools.zip_longest()
```

```python
import itertools

numbers = [1, 2, 3, 4, 5]
cumulative_sum = itertools.accumulate(numbers)
print(list(cumulative_sum))  # Output: [1, 3, 6, 10, 15]

import operator

numbers = [1, 2, 3, 4, 5]
cumulative_product = itertools.accumulate(numbers, operator.mul)
print(list(cumulative_product))  # Output: [1, 2, 6, 24, 120]

values = [3, 1, 4, 1, 5, 9, 2]
cumulative_max = itertools.accumulate(values, max)
print(list(cumulative_max))  # Output: [3, 3, 4, 4, 5, 9, 9]

numbers = [1, 2, 3]
cumulative_sum_with_initial = itertools.accumulate(numbers, initial=10)
print(list(cumulative_sum_with_initial)) # Output: [10, 11, 13, 16]
```

### Functools

```python
from functools import lru_cache
@lru_cache(None)
def dfs(x):
    xxxxx
```

### Random

* ```python
  import math

  # Floor division (rounds towards negative infinity)
  print(f"5 // 2: {5 // 2}")     #  2
  print(f"-5 // 2: {-5 // 2}")   # -3

  # Truncation towards zero (using math.trunc)
  print(f"math.trunc(5 / 2): {math.trunc(5 / 2)}")    #  2
  print(f"math.trunc(-5 / 2): {math.trunc(-5 / 2)}")  # -2
  ```
