# Day20 : Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum, and return its sum.

**Test Cases**
1. Input: nums = [5,4,-1,7,8]    Output: 23
2. Input: nums = [-1,-2,-3,-4]   Output: -1

**Intuition**
1. A brute-force way would be to check all possible subarrays and find their sums, but that’s too slow (O(n^2) or O(n^3)).Instead, notice:
2. If the previous sum is negative, it will only reduce the total, so start a new subarray.
3. If the previous sum is positive, extend it, because it will increase the total.

**Algorithm** 
1. Initialize two variables:
2. max_sum = nums[0] → stores the result (maximum subarray sum found so far).
3. current_sum = nums[0] → stores the current subarray sum.
4. Traverse the array from index 1 to n-1:
5. At each step, decide:
     current_sum = max(nums[i], current_sum + nums[i])
6. Either start a new subarray from current element OR extend the existing subarray.
7. Update result:
   max_sum = max(max_sum, current_sum)
8.Return max_sum.

**Complexity Analysis**
Time Complexity: O(n)
Space Complexity: O(1)

