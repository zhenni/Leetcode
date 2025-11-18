---
icon: bell-ring
---

# Reminder

* Long int:
  * C++: For integers, there are int, long int, and long long&#x20;
    * [https://stackoverflow.com/questions/18971732/what-is-the-difference-between-long-long-long-long-int-and-long-long-i](https://stackoverflow.com/questions/18971732/what-is-the-difference-between-long-long-long-long-int-and-long-long-i)
  * Python: [https://stackoverflow.com/questions/2104884/how-does-python-manage-int-and-long](https://stackoverflow.com/questions/2104884/how-does-python-manage-int-and-long)
* Truncation for negative integers
  *   Python

      ```python
      # Floor division (rounds towards negative infinity)
      print(f"5 // 2: {5 // 2}")     #  2
      print(f"-5 // 2: {-5 // 2}")   # -3

      # Truncation towards zero (using math.trunc)
      print(f"math.trunc(5 / 2): {math.trunc(5 / 2)}")    #  2
      print(f"math.trunc(-5 / 2): {math.trunc(-5 / 2)}")  # -2
      ```
