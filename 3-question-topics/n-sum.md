# N-Sum

* No.1  2-Sum: Hashmap(O(n))
* No. 1679: Max Number of K-Sum Pairs. 2-sum
* No. 1711: Count Good Meals. 2-Sum
* No. 2006:  Count Number of Pairs With Absolute Difference K. 2-Sum
* No.167 2-Sum ||, sorted array: 2 pointer O(n), hashmap O(n), binary-search O(nlogn)
* No.170 2-Sum III, implement class: same
* No.653 2-Sum IV, input is BST: same No.167



* No.1099: Two Sum Less Than K
  * sort, can stop early
  * sort+2pointer O(nlogn+n)
  * sort+binary search O(nlogn+nlogn)
  * isSeen flag array for the array. O(n+max(num)) 2-pointer



* No.15 3-Sum:&#x20;
  * avoid duplicate solution
  * fix one number -> 2Sum
    * sort+2 pointer(O(n^2)) with 2-sumII
    * sort+hashmap(O(n^2))  with 2-sum space O(n)
* No.16 3-Sum closest: same No.15
* No. 259: 3Sum Smaller
  * fix on number -> 2sum smaller



* No.18 4-Sum: Using 3-Sum? Better than O(n^3)?
* No.454 4-Sum II: HashMap(O(n^2))





No.170

[http://www.cnblogs.com/grandyang/p/5184143.html](http://www.cnblogs.com/grandyang/p/5184143.html)

Design and implement a TwoSum class. It should support the following operations: add and find.

add - Add the number to an internal data structure.\
find - Find if there exists any pair of numbers which sum is equal to the value.

For example,

```
add(1); 
add(3); 
add(5);
find(4) -
>
 true
find(7) -
>
 false
```
