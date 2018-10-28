* No.  10: Regular Expression Matching: 2D DP (P[i][j] to be true if s[0..i) matches p[0..j) and false otherwise; many cases thinking) [sol](https://discuss.leetcode.com/topic/17852/9-lines-16ms-c-dp-solutions-with-explanations)
* No.  44: Wildcard Matching: similar to 10
* No.  32: Longest Valid Parentheses: 
    - DP [1D array DP]: array longest[], for any longest[i], it stores the longest length of valid parentheses which is end at i.
` if s[i-1] is ')' and s[i-longest[i-1]-1] == '(', longest[i] = longest[i-1] + 2 + longest[i-longest[i-1]-2]`
    - DP with stack: idea similar to 1D array DP
    - (2D DP is obviously) 
* No. 221 Maximal Square: dp[i][j]: the largest side of squares with point [i, j] as bottom right corner
* No. 139: Word Break: `canBreak[i] = True if canBreak[j] and (s[j:i] in wordDict) for j < i`


Reference Links:
    - [http://ryanleetcode.blogspot.com/2015/07/blog-post_16.html](http://ryanleetcode.blogspot.com/2015/07/blog-post_16.html)

## When to use DP?

- Input cannot sort
- Find minimum/maximum result
    - Optimal solution, optimal substructure
- Check the feasibility
- Count all possible solutions

1. Optimal Substruction: The optimal solution to the problem contains all the optimal solutions to its sub-problems.
2. No after-effect. The previous result is fixed, which will not be affected by any later actions.
3. Substructures may have some interactions. The optimal solutions to some sub-problems will be used for some other problems in the next decision steps.


## 4 Types of DP

1. Matrix DP (10%)
2. Sequence (40%)
3. Two Sequences DP (40%)*
4. Backpack (10%)

### Solutions
1. State
2. Function. State transition function
3. Initialization. The solutions to the smallest problem.
4. Answer. The solution to the original problem.

1. Matrix DP
    1. State: f[x][y]. From [0, 0] to [x, y].
    2. Function: How the path from [0, 0] to [x, y] looks like.
    3. Intialization: f[0][0]
    4. Answer: f[m][n]
2. Sequence Dp
    1. State: f[i]: The state for the previous i position/number/character
    2. Function: f[i] = f[j].... (i < j)
    3. Intialization: f[0]
    4. Answer: f[n]
3. Two Sequences Dp
    1. State: f[i][j]: s1[0..i] and s2[0..j] are matched
    2. Function: f[i][j]: How are they matched?
    3. Intialization: f[i][0] and f[0][j]
    4. answer: f[s1.length()][s2.length()]

    - Scramble String(3 sequences)
        - f[i][j][len]: s1[i..i+len] and s2[j..j+len] are matched
