# 217. Contains Duplicate

**Difficulty:** Easy

## Problem
Given an integer array `nums`, return `True` if any value appears at least twice; otherwise, return `False`.

## Solution 1: Hash Set

```python
class Solution:
    def containsDuplicate(self, nums: list[int]) -> bool:
        hs = set()
        for i in nums:
            if i not in hs:
                hs.add(i)
            else:
                return True
        return False
```

- **Time Complexity:** `O(n)`
- **Space Complexity:** `O(n)`

## Solution 2: Pythonic Approach (Best)

```python
class Solution:
    def containsDuplicate(self, nums: list[int]) -> bool:
        return len(set(nums)) < len(nums)
```

**Explanation:** A set stores only unique elements. If the set's length is smaller than the original array's length, duplicates exist.

- **Time Complexity:** `O(n)` average
- **Space Complexity:** `O(n)`

## Example

**Input:** `nums = [1, 2, 3, 1]`  
**Output:** `True`

**Input:** `nums = [1, 2, 3, 4]`  
**Output:** `False`

## Key Takeaway
Both solutions use a hash set and have `O(n)` average time complexity. Solution 1 returns early when a duplicate is found, while Solution 2 is shorter and more Pythonic.
