

# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
- The problem asks whether there exist two non-negative integers, a and b, such that a^2 + b^2 = c. One possible approach is to use a two-pointer technique where you start with the smallest and largest possible values of a and b and move towards each other until you find a pair that satisfies the equation.
----

![Screenshot (47).png](https://assets.leetcode.com/users/images/dcb50c20-6812-4e7c-a22f-e5d51e1f8611_1706276343.5395696.png)


----
# Approach
<!-- Describe your approach to solving the problem. -->

1. Initialize two pointers, start and end, where start is at 0 and end is at the square root of c.
2. In each iteration, calculate the sum of squares (ans = start^2 + end^2).
3. If ans is equal to c, return true as you have found a pair (a, b) that satisfies the equation.
4. If ans is greater than c, decrement end to try smaller values.
5. If ans is less than c, increment start to try larger values.
6. Repeat steps 2-5 until start becomes greater than end.
7. If the loop completes without finding a pair, return false.

---


# Complexity

- **Time complexity: O(sqrt(c))** - The algorithm runs in linear time with respect to the square root of c.


- **Space complexity: O(1)** - The algorithm uses a constant amount of extra space regardless of the input size.

----

# Code
```
class Solution {
public:
    bool judgeSquareSum(int c) 
    {
        long long int start=0;
        long long int end=sqrt(c);
        while(start<=end)
        {
            long long int ans=start*start + end*end;
            if(ans==c)
                return true;
            else if(ans>c)
                end--;
            else
                start++;
        }    
        return false;
    }
};
```
