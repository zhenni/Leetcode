# Subarray and Substring

### SubArray:

* [643. Maximum Average Subarray I](https://leetcode.com/problems/maximum-average-subarray-i/): sliding window
* No. 53:  Maximum Subarray: dynamic programming: keep the variable of maxEndingHere
* No. 152: Maximum Product Subarray
* No. 209: Minimum Size Subarray Sum (all positive number) 2 pointer
* No. 239: Sliding Window Maximum:
  * [Two Simple Pass, calculating maximum from two side](https://discuss.leetcode.com/topic/26480/o-n-solution-in-java-with-two-simple-pass-in-the-array)
  * Queue, only save the numbers that may be as a maximum, which always is the front of the queue
* No. 325: Maximum Size Subarray Sum Equals k: mod + presix sum + hashmap [https://segmentfault.com/a/1190000005771068](https://segmentfault.com/a/1190000005771068)
* No. 523: Continuous Subarray Sum: target is n times k: Hashmap, Consider cases
* No. 974: Subarray Sums Divisible by K. Same as 523
* No. 560: Subarray sum equals K: Presum+2-sum
* No. 713: Subarray Product Less Than K:&#x20;
  * log -> n-sum. prefix sum. binary search
  * 2 pointer O(n)
    * heap ??&#x20;
    * Deque [link](https://discuss.leetcode.com/topic/19055/java-o-n-solution-using-deque-with-explanation)
    * [O(n) solution in Java with two simple pass in the array](https://discuss.leetcode.com/topic/26480/o-n-solution-in-java-with-two-simple-pass-in-the-array)

### Substring

* No. 30: Substring with Concatenation of All Words

&#x20; two-pointer + hash map/set

* [3. Longest Substring Without Repeating Characters](https://leetcode.com/problems/longest-substring-without-repeating-characters/)
* No. 76: Minimum Window Substring : 2pointer + hashmap
