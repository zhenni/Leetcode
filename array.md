Sum:

* No. 303: Range Sum Query Immutable: prefix sum
* No. 304: Range Sum Query 2D Immutable: integral image

* No. 416: Partition Equal Subset Sum: sum, dp(backpack) (use bit to reduce space );
    * Extention:
    http://www.geeksforgeeks.org/partition-a-set-into-two-subsets-such-that-the-difference-of-subset-sums-is-minimum/
* No. 698: Partition to K Equal Sum Subsets: dfs


Product

* No. 238: Product of Array Except Self: Two times calculation O\(n\)


Majority:
* No. 373 Find K Pairs with Smallest Sums: **Moore Voting Algorithm** [https://discuss.leetcode.com/topic/17446/6-suggested-solutions-in-c-with-explanations](https://discuss.leetcode.com/topic/17446/6-suggested-solutions-in-c-with-explanations) one counter
* No. 229 Majority Element II: Moore Voting Algorithm: two counter

Other:

* No. 189 Rotate Array: Copy; O(1)-tmp memory; Reverse two set and Reverse all
* No. 632: Smallest Range: K merge sort
* No. 697: Degree of an Array: Hashmap


Stock:
* No. 121: Best Time to Buy and Sell Stock: (one whole transaction) [Kadane's Algorithm(similar to maximum subarray, using difference between neighbors)](https://discuss.leetcode.com/topic/19853/kadane-s-algorithm-since-no-one-has-mentioned-about-this-so-far-in-case-if-interviewer-twists-the-input)
* No. 122: Best Time to Buy and Sell Stock II: (multiple times transactions) simple
* No. 123: Best Time to Buy and Sell Stock III: 
    - (2 times -> k times) DP : f[k, ii] represents the max profit up until prices[ii] (Note: NOT ending with prices[ii]) using at most k transactions. 
    - Thinking: max k subarray sum
    - some states: states[][0]: one buy; states[][1]: one buy, one sell; states[][2]: two buys, one sell; states[][3]: two buy, two sell [sol](https://discuss.leetcode.com/topic/19750/my-c-solution-o-n-time-o-1-space-8ms)
* No. 188: Best Time to Buy and Sell Stock IV: 
    - [sol Using DP solution with O(kn) time O(k) space](https://discuss.leetcode.com/topic/12250/share-my-c-dp-solution-with-o-kn-time-o-k-space-10ms)
    - [sol Using O(n + klgn) time using Max Heap and Stack](https://discuss.leetcode.com/topic/9522/c-solution-with-o-n-klgn-time-using-max-heap-and-stack) keep the highest k ones.(not the best)   
* No. 
