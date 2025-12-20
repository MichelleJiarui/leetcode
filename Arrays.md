https://leetcode.cn/problems/two-sum/solutions/434597/liang-shu-zhi-he-by-leetcode-solution/

方法一：暴力枚举
思路及算法

最容易想到的方法是枚举数组中的每一个数 x，寻找数组中是否存在 target - x。

当我们使用遍历整个数组的方式寻找 target - x 时，需要注意到每一个位于 x 之前的元素都已经和 x 匹配过，因此不需要再进行匹配。而每一个元素不能被使用两次，所以我们只需要在 x 后面的元素中寻找 target - x。


Here is the code reformatted into GitHub-flavored Markdown. I’ve added a header and syntax highlighting to make it look clean and professional for a README or documentation file.

# Leetcode 1 Two Sum Solution

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

Here is the reformatted content in a clean, professional GitHub Markdown format. I’ve organized it into a structured list with clear headings and useful links.

# Leetcode 26. Remove Duplicates from Sorted Array

**Difficulty:** Easy

**Topic:** Two Pointers / Array

* **Problem Link:** [LeetCode #26 - Remove Duplicates from Sorted Array](https://leetcode.cn/problems/remove-duplicates-from-sorted-array/description/)
* **Video Tutorial:** [Watch on YouTube](https://www.youtube.com/watch?v=DEJAZBq0FDA)

---

太好了 👍
这个需求**非常关键**，学会这个你能直接秒一大批数组题。

下面我把它总结成一个 **「万能快慢指针模板」**，并告诉你**什么时候改哪一行**。

---

# 🚀 万能快慢指针模板（数组原地修改）

## 🎯 核心思想（一句话）

> **fast 负责扫描，slow 负责保存有效结果**

---

## 🧠 通用模板（必背）

```python
slow = 0
for fast in range(len(nums)):
    if 满足条件(nums[fast]):
        nums[slow] = nums[fast]
        slow += 1

return slow
```

📌 **含义**

* `fast`：遍历所有元素
* `slow`：指向「下一个可写位置」
* `[0, slow)`：始终是 **合法答案区间**

---

## 🧩 模板拆解（记住这 3 点）

### 1️⃣ fast 永远走全程

```python
for fast in range(len(nums)):
```

👉 **不回头、不停**

---

### 2️⃣ if 决定“要不要这个元素”

```python
if 满足条件:
```

你只需要改这里！

---

### 3️⃣ slow 只在“保留元素”时移动

```python
nums[slow] = nums[fast]
slow += 1
```

---

# 📘 套路实例（从你这题开始）

---

## 例 1️⃣ 去重（LeetCode 26）

**条件**：当前值 ≠ 前一个值

```python
slow = 1
for fast in range(1, len(nums)):
    if nums[fast] != nums[fast - 1]:
        nums[slow] = nums[fast]
        slow += 1
return slow
```

---

## 例 2️⃣ 允许重复两次（LeetCode 80）

**条件**：不能出现 3 个相同的

```python
slow = 2
for fast in range(2, len(nums)):
    if nums[fast] != nums[slow - 2]:
        nums[slow] = nums[fast]
        slow += 1
return slow
```

🧠 **技巧**：看 `slow - k`

---

## 例 3️⃣ 移除指定元素（LeetCode 27）

**条件**：不是目标值

```python
slow = 0
for fast in range(len(nums)):
    if nums[fast] != val:
        nums[slow] = nums[fast]
        slow += 1
return slow
```

---

## 例 4️⃣ 移动零（LeetCode 283）

**条件**：非零

```python
slow = 0
for fast in range(len(nums)):
    if nums[fast] != 0:
        nums[slow] = nums[fast]
        slow += 1
```

---

## 🧠 快速判断用哪种套路？

### 问自己 3 个问题：

| 问题            | 是 → 用快慢指针 |
| ------------- | --------- |
| 要原地修改数组？      | ✅         |
| 顺序能改变吗？       | ❌         |
| 返回长度 or 有效前缀？ | ✅         |

---

## 🧩 万能口诀（考试用）

```
fast 找路
slow 填坑
if 决定留不留
[0, slow) 是答案
```

---

## ⚠️ 常见错误（避坑）

❌ slow 每轮都加
❌ fast / slow 同时动
❌ if 条件写错比较对象

---

## 🧠 一眼识别这类题

题目出现这些词，**直接快慢指针**：

* remove
* deduplicate
* in-place
* keep order
* return length

---

如果你愿意，我可以下一步帮你：

* 把这个模板整理成 **一张速查表**
* 或出 **3 道练习题 + 手把手画图**
* 或对比 **快慢指针 vs 双端指针**

你已经掌握“面试高频核心套路”了 👏




