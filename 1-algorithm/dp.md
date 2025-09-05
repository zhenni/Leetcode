# Dynamic Programming

1. Matrix DP
   * No.  62: Unique Paths (Can be solved by math)
   * No.  63: Unique Paths II
   * No.  64: Minimum Path Sum
   * No. 120: Triangle
   * No. 221 Maximal Square: dp\[i]\[j]: the largest side of squares with point \[i, j] as bottom right corner
2. Sequences DP
   * No.  53: Maximum Subarray  (Can do state reduction)
   * No. 152: Maximum Product Subarray. similar to 53
   * No. 139: Word Break: `canBreak[i] = True if canBreak[j] and (s[j:i] in wordDict) for j < i`
   * No. 139: Word Break II
   * No.  32: Longest Valid Parentheses:
     *   DP \[1D array DP]: array longest\[], for any longest\[i], it stores the longest length of valid parentheses which is end at i.

         `if s[i-1] is ')' and s[i-longest[i-1]-1] == '(', longest[i] = longest[i-1] + 2 + longest[i-longest[i-1]-2]`
     * DP with stack: idea similar to 1D array DP
   * No.  70: Climbing Stairs
     * Fibonacci Number: Binets Method & Fibonacci Formula
   * No. 746: Min Cost Climbing Stairs
   * No.  91: Decode Ways
   * No. 639: Decode Ways II
   * No.  96: Unique Binary Search Trees
     * f\[i] = sum (f\[j-1] \* f\[i-j]) : j as a root
     * (Math deduction)
   * No.  95: Unique Binary Search Trees II: Tree structure
   * No. 131: Palindrome Partitioning. Need DFS backtrace
   * No. 132: Palindrome Partitioning II.
   * No. 121: Best Time to Buy and Sell Stock: (one whole transaction) [Kadane's Algorithm(similar to maximum subarray, using difference between neighbors)](https://discuss.leetcode.com/topic/19853/kadane-s-algorithm-since-no-one-has-mentioned-about-this-so-far-in-case-if-interviewer-twists-the-input)
   * No. 123: Best Time to Buy and Sell Stock III:
     * (2 times -> k times) DP : f\[k, ii] represents the max profit up until prices\[ii] (Note: NOT ending with prices\[ii]) using at most k transactions.
     * Thinking: max k subarray sum
     * some states: states\[]\[0]: one buy; states\[]\[1]: one buy, one sell; states\[]\[2]: two buys, one sell; states\[]\[3]: two buy, two sell [sol](https://discuss.leetcode.com/topic/19750/my-c-solution-o-n-time-o-1-space-8ms)
   * No. 188: Best Time to Buy and Sell Stock IV:
     * [sol Using DP solution with O(kn) time O(k) space](https://discuss.leetcode.com/topic/12250/share-my-c-dp-solution-with-o-kn-time-o-k-space-10ms) hold\[i], release\[i]
     * [sol Using O(n + klgn) time using Max Heap and Stack](https://discuss.leetcode.com/topic/9522/c-solution-with-o-n-klgn-time-using-max-heap-and-stack) keep the highest k ones.(not the best)
   * No. 1823: Find the Winner of the Circular Game: [Simulate from small problem](https://leetcode.com/problems/find-the-winner-of-the-circular-game/solutions/5438619/rust-elixir-bottom-up-dp-for-follow-up/)
3. Two Sequences Dp
   * No.  10: Regular Expression Matching: 2D DP (P\[i]\[j] to be true if s\[0..i) matches p\[0..j) and false otherwise; many cases thinking) [sol](https://discuss.leetcode.com/topic/17852/9-lines-16ms-c-dp-solutions-with-explanations)
   * No.  44: Wildcard Matching: similar to 10
   * No.  72: Edit Distance (Can do state reduction)
   * No.  96: Interleaving String : s1\[0...i], s2\[0..j], s3\[0..i+j]
   * No. 115: Distinct Subsequences (Can do state reduction)
   * No. 87: Scramble String. 2 Sequence + Length. f\[i]\[j]\[len]: s1\[i..i+len] and s2\[j..j+len] are matched

#### Reference Links:

* [http://ryanleetcode.blogspot.com/2015/07/blog-post\_16.html](http://ryanleetcode.blogspot.com/2015/07/blog-post_16.html)

## When to use DP?

* Input cannot sort
* Find minimum/maximum result
  * Optimal solution, optimal substructure
* Check the feasibility
* Count all possible solutions
* Optimal Substruction: The optimal solution to the problem contains all the optimal solutions to its sub-problems.
* No after-effect. The previous result is fixed, which will not be affected by any later actions.
* Substructures may have some interactions. The optimal solutions to some sub-problems will be used for some other problems in the next decision steps.

## 4 Types of DP

1. Matrix DP (10%)
2. Sequence (40%)
3. Two Sequences DP (40%)\*
4. Backpack (10%)
5. Need Backtrace （DFS）

### Solutions

* State
* Function. State transition function
* Initialization. The solutions to the smallest problem.
* Answer. The solution to the original problem.
* Optimization: State reduction.
* Matrix DP 1. State: f\[x]\[y]. From \[0, 0] to \[x, y]. 2. Function: How the path from \[0, 0] to \[x, y] looks like. 3. Intialization: f\[0]\[0] 4. Answer: f\[m]\[n]
* Sequence Dp
  1. State: f\[i]: The state for the previous i position/number/character
  2. Function: f\[i] = f\[j].... (i < j)
  3. Intialization: f\[0]
  4. Answer: f\[n]
* Two Sequences Dp 1. State: f\[i]\[j]: s1\[0..i] and s2\[0..j] are matched 2. Function: f\[i]\[j]: How are they matched? 3. Intialization: f\[i]\[0] and f\[0]\[j] 4. answer: f\[s1.length()]\[s2.length()]
  * Scramble String(3 sequences)
    * f\[i]\[j]\[len]: s1\[i..i+len] and s2\[j..j+len] are matched
