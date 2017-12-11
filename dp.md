* No.  10: Regular Expression Matching: 2D DP (P[i][j] to be true if s[0..i) matches p[0..j) and false otherwise; many cases thinking) [sol](https://discuss.leetcode.com/topic/17852/9-lines-16ms-c-dp-solutions-with-explanations)
* No.  32: Longest Valid Parentheses: 
    - DP [1D array DP]: array longest[], for any longest[i], it stores the longest length of valid parentheses which is end at i.
` if s[i-1] is ')' and s[i-longest[i-1]-1] == '(', longest[i] = longest[i-1] + 2 + longest[i-longest[i-1]-2]`
    - DP with stack: idea similar to 1D array DP
    - (2D DP is obviously) 
* No.