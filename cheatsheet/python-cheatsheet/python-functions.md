# Python Functions

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

```
# python built-in:
a = [1, 2, 3]
b = ['a', 'b']

list(zip(a, b))
# [(1, 'a'), (2, 'b')]
```
