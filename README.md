# 2176. Count Equal and Divisible Pairs in an Array

## 📝 Problem Statement

Given a **0-indexed** integer array `nums` of length `n` and an integer `k`, return the number of **pairs** `(i, j)` where:

- `0 <= i < j < n`
- `nums[i] == nums[j]`
- `(i * j) % k == 0`

---

## 📌 Example 1

**Input:**
```
nums = [3,1,2,2,2,1,3]
k = 2
```
# Output:
```
4
```
# Explanation: Valid pairs are:

+ (0, 6): nums[0] == nums[6], and 0 * 6 = 0 (divisible by 2)

+ (2, 3): nums[2] == nums[3], and 2 * 3 = 6 (divisible by 2)

+ (2, 4): nums[2] == nums[4], and 2 * 4 = 8 (divisible by 2)

+ (3, 4): nums[3] == nums[4], and 3 * 4 = 12 (divisible by 2)


# ✅ Constraints
+ 1 <= nums.length <= 100

+ 1 <= nums[i], k <= 100

# 💡 Approach
1. Use a nested loop to go through all possible pairs (i, j) where i < j.

2. Check if:

+ nums[i] == nums[j]

+ (i * j) % k == 0

3. Count the number of such valid pairs.

# 🧠 Python Solution
```
class Solution(object):
    def countPairs(self, nums, k):
        """
        :type nums: List[int]
        :type k: int
        :rtype: int
        """
        count = 0
        n = len(nums)
        
        for i in range(n):
            for j in range(i + 1, n):
                if nums[i] == nums[j] and (i * j) % k == 0:
                    count += 1
                    
        return count
```
# 🔁 Time & Space Complexity
+ Time Complexity: O(n²)
  (Nested loop, but acceptable since n ≤ 100)

+ Space Complexity: O(1)
  (No extra space used apart from a counter)

