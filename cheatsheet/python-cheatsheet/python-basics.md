---
description: Some functions may not use in daily coding but may use in Leetcode problems
---

# Python Basics

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

### List

* `nums.sort()`: Sorts the list in-place. `O(nlogn)`
  * `sorted(nums)` : Returns a **new list** that is sorted.
* `[x + y for x in nums]`: iterating through a nested list. `O(n)`
* `nums.insert(index, x)`: Inserts `x` at the specified `index` in the list. `O(n)` in the worst case.
* `nums.index(x)` :Returns the **first index** of the element `x` in the list. `O(n)`
* `nums.remove(x)`: Removes the **first occurrence** of `x` from the list. `O(n)` in the worst case.
  * If `x` is not in the list, it raises a `ValueError`.&#x20;
* `nums.pop(index)` : Removes and returns the element at the specified `index`. `O(n)`
  * `nums.pop()`: If no index is specified, it removes and returns the **last item.** `O(1)`
* `nums.clear()` : Removes all elements from the list. `O(n)`&#x20;
* `nums[::-1]` : Reverse `O(n)`
* `nums.count(x)` : Returns the **number of occurrences** of `x` in the list. `O(n)`
* `zip(list1, list2)`: Combines two (or more) iterables (like lists) into an iterator of tuples, where the `i`-th tuple contains the `i`-th element from each iterable. `O(min(n,m))`
  * ```python
    list1 = [1, 2, 3]
    list2 = ['a', 'b', 'c', 'd']
    zipped = list(zip(list1, list2))  # Output: [(1, 'a'), (2, 'b'), (3, 'c')]
    ```
* `map(func, iterable)` : Applies a function `func` to each item of the iterable and returns an iterator yielding the results. `O(n)`
  * ```python
    nums = [1, 2, 3, 4]
    squared = list(map(lambda x: x ** 2, nums))  # Output: [1, 4, 9, 16]
    ```
* `filter(func, iterable)`: Filters elements from the iterable where `func` returns `True` and returns an iterator of the filtered results. `O(n)`
  * ```python
    nums = [1, 2, 3, 4, 5]
    even = list(filter(lambda x: x % 2 == 0, nums))  # Output: [2, 4]
    ```

