# Bit Operation

1. _**A^A=0**_
2. _**A^B^A=B**_
3. _**(A^A^B) = (B^A^A) = (A^B^A) = B**_ This shows that position doesn't matter.



* [136. Single Number](https://leetcode.com/problems/single-number/)



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
