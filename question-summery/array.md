# Array

## Sum

* No. 303: Range Sum Query Immutable: prefix sum
* No. 304: Range Sum Query 2D Immutable: integral image
* No. 416: Partition Equal Subset Sum: sum, dp(backpack) (use bit to reduce space );
  *   Extention:

      [http://www.geeksforgeeks.org/partition-a-set-into-two-subsets-such-that-the-difference-of-subset-sums-is-minimum/](http://www.geeksforgeeks.org/partition-a-set-into-two-subsets-such-that-the-difference-of-subset-sums-is-minimum/)
* No. 698: Partition to K Equal Sum Subsets: dfs

## Product

* No. 238: Product of Array Except Self: Two times calculation O(n)

## Majority

* No. 373 Find K Pairs with Smallest Sums: **Moore Voting Algorithm** [https://discuss.leetcode.com/topic/17446/6-suggested-solutions-in-c-with-explanations](https://discuss.leetcode.com/topic/17446/6-suggested-solutions-in-c-with-explanations) one counter
* No. 229 Majority Element II: Moore Voting Algorithm: two counter

## Max Consecutive&#x20;

* No. 485: Max Consecutive Ones
* No. 487: Max Consecutive Ones II [https://eugenejw.github.io/2017/08/leetcode-487](https://eugenejw.github.io/2017/08/leetcode-487) (also applicable to 1004)
*   No. 1004: Max Consecutive Ones III

    * O(1) space: moving window
    * time: queue


* No. 1446: Consecutive Characters (485)
* No. 1869: Longer Contiguous Segments of Ones than Zeros (485)
* No. 1784: Check if Binary String Has at Most One Segment of Ones (485)
* No. 1550: Three Consecutive Odds (485)



* No. 128: Longest Consecutive Sequence: Hashing
* No. 829: Consecutive Numbers Sum: calculation O(sqrt(N))

## Amplitude

* &#x20;No. 1509: Minimum Difference Between Largest and Smallest Value in Three Moves:&#x20;
  * sort O(nlogn)
  * O(n). save (k+1) min and (k+1) max
  * extend to k moves. min-heap and max-heap. O(nlogk) time [https://leetcode.com/problems/minimum-difference-between-largest-and-smallest-value-in-three-moves/discuss/1729942/Python3-(very)-simple-heapq-O(n-log-k)-99-memory](https://leetcode.com/problems/minimum-difference-between-largest-and-smallest-value-in-three-moves/discuss/1729942/Python3-\(very\)-simple-heapq-O\(n-log-k\)-99-memory)
* Google Find the min amplitude after removing K consecutive elements in an array. [https://leetcode.com/discuss/interview-question/1523646/google-find-the-min-amplitude-after-removing-k-consecutive-elements-in-an-array](https://leetcode.com/discuss/interview-question/1523646/google-find-the-min-amplitude-after-removing-k-consecutive-elements-in-an-array)
  * window-left min and max, window-right min and max. O(n) time. O(n) space.



## Stock:

* No. 121: Best Time to Buy and Sell Stock: (one whole transaction) [Kadane's Algorithm(similar to maximum subarray, using difference between neighbors)](https://discuss.leetcode.com/topic/19853/kadane-s-algorithm-since-no-one-has-mentioned-about-this-so-far-in-case-if-interviewer-twists-the-input)
* No. 122: Best Time to Buy and Sell Stock II: (multiple times transactions) simple
* No. 123: Best Time to Buy and Sell Stock III:&#x20;
  * (2 times -> k times) DP : f\[k, ii] represents the max profit up until prices\[ii] (Note: NOT ending with prices\[ii]) using at most k transactions.&#x20;
  * Thinking: max k subarray sum
  * some states: states\[]\[0]: one buy; states\[]\[1]: one buy, one sell; states\[]\[2]: two buys, one sell; states\[]\[3]: two buy, two sell [sol](https://discuss.leetcode.com/topic/19750/my-c-solution-o-n-time-o-1-space-8ms)
* No. 188: Best Time to Buy and Sell Stock IV:&#x20;
  * [sol Using DP solution with O(kn) time O(k) space](https://discuss.leetcode.com/topic/12250/share-my-c-dp-solution-with-o-kn-time-o-k-space-10ms)
  * [sol Using O(n + klgn) time using Max Heap and Stack](https://discuss.leetcode.com/topic/9522/c-solution-with-o-n-klgn-time-using-max-heap-and-stack) keep the highest k ones.(not the best)  &#x20;
* No. 309: Best Time to Buy and Sell Stock with Cooldown
  * DP: [https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/discuss/?currentPage=1\&orderBy=hot\&query=](https://leetcode.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/discuss/?currentPage=1\&orderBy=hot\&query=)
*   No. 714: Best Time to Buy and Sell Stock with Transaction Fee: Dynamic programming with 2 variables: hold and sell. O(n) time & O(1) space









## Other:

* No. 189 Rotate Array: Copy; O(1)-tmp memory; Reverse two set and Reverse all
* No. 632: Smallest Range: K merge sort
* No. 697: Degree of an Array: Hashmap
