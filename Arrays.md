https://leetcode.cn/problems/two-sum/solutions/434597/liang-shu-zhi-he-by-leetcode-solution/

方法一：暴力枚举
思路及算法

最容易想到的方法是枚举数组中的每一个数 x，寻找数组中是否存在 target - x。

当我们使用遍历整个数组的方式寻找 target - x 时，需要注意到每一个位于 x 之前的元素都已经和 x 匹配过，因此不需要再进行匹配。而每一个元素不能被使用两次，所以我们只需要在 x 后面的元素中寻找 target - x。


Here is the code reformatted into GitHub-flavored Markdown. I’ve added a header and syntax highlighting to make it look clean and professional for a README or documentation file.

# Two Sum Solution

## Problem Description

The goal is to find two indices in an array such that the numbers at those positions add up to a specific target.

## Implementation

This implementation uses a **Brute Force** approach with nested loops.

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        for i in range(n):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]
        
        return []

```

---

### Complexity Analysis

* **Time Complexity:** O(n^2) — The algorithm uses two nested loops to iterate through the list.
* **Space Complexity:** O(1) — No extra space is used regardless of the input size.

26RemoveDuiplicate
Remove Duplicates from Sorted Array 
https://leetcode.cn/problems/remove-duplicates-from-sorted-array/description/ 
https://www.youtube.com/watch?v=DEJAZBq0FDA
