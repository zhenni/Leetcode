# Two Pointers

* No. 287: Fast and slow pointer. Find circle in a linked list.



* No. 26: Remove Duplicates from Sorted Array
* No. 27: Remove Element
* No. 80: Remove Duplicates from Sorted Array II



* No. 283: Move Zeroes: In-place solution
  * All elements before the slow pointer (lastNonZeroFoundAt) are non-zeroes.
  * All elements between the current and slow pointer are zeroes.
  * swap(nums\[lastNonZeroFoundAt++], nums\[cur]);
  * worst case faster

