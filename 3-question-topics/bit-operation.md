# Bit Operation

1. _**A^A=0**_
2. _**A^B^A=B**_
3. _**(A^A^B) = (B^A^A) = (A^B^A) = B**_ This shows that position doesn't matter.



* [136. Single Number](https://leetcode.com/problems/single-number/)



{% code overflow="wrap" %}
```
x << y
Returns x with the bits shifted to the left by y places (and new bits on the right-hand-side are zeros). This is the same as multiplying x by 2**y.
x >> y
Returns x with the bits shifted to the right by y places. This is the same as floor division of x by 2**y.
x & y
Does a "bitwise and". Each bit of the output is 1 if the corresponding bit of x AND of y is 1, otherwise it's 0.
x | y
Does a "bitwise or". Each bit of the output is 0 if the corresponding bit of x AND of y is 0, otherwise it's 1.
~ x
Returns the complement of x - the number you get by switching each 1 for a 0 and each 0 for a 1. This is the same as -x - 1.
x ^ y
Does a "bitwise exclusive or". Each bit of the output is the same as the corresponding bit in x if that bit in y is 0, and it's the complement of the bit in x if that bit in y is 1.
```
{% endcode %}

* [338. Counting Bits](https://leetcode.com/problems/counting-bits/)





n & (n-1): remove the first one

* No. 191: Number of 1 Bits:  n & (n-1)



* No. 231: Power of Two: n & (n-1)
* No. 326: Power of Three: Max3PowerInt / this number
* No. 342: Power of Four: ((num-1)\&num)==0 && (num-1)%3==0; OR consider 1010101010101010101010101010101 (1431655765)



*   No. [2749. Minimum Operations to Make the Integer Zero](https://leetcode.com/problems/minimum-operations-to-make-the-integer-zero/)

    * Many languages offer built-in popcount functions:
      * C++: `__builtin_popcountll(x)` for `long long`.
      * Java: `Long.bitCount(x)`.
      * C#: `BitOperations.PopCount((ulong)s)` (or manual bit counting if unavailable).
      * Python: `bin(x).count('1')` or use `x.bit_count()` in Python 3.8+.

    If a built-in is unavailable, implement a small function that counts set bits (e.g., `while(x) { count += x & 1; x >>= 1; }`).

    \
