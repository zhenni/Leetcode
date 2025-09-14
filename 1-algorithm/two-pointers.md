# Two Pointers

* No. 287: Fast and slow pointer. Find circle in a linked list.
* [121. Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)



* No. 26: Remove Duplicates from Sorted Array
* No. 27: Remove Element
* No. 80: Remove Duplicates from Sorted Array II



* No. 283: Move Zeroes: In-place solution
  * All elements before the slow pointer (lastNonZeroFoundAt) are non-zeroes.
  * All elements between the current and slow pointer are zeroes.
  * swap(nums\[lastNonZeroFoundAt++], nums\[cur]);
  * worst case faster

