# Leetcode

## 1. Array

### Day 1



#####  **704. 二分查找** 

**题目建议**： 大家能把 704 掌握就可以，35.搜索插入位置 和 34. 在排序数组中查找元素的第一个和最后一个位置 ，如果有时间就去看一下，没时间可以先不看，二刷的时候在看。



先把 704写熟练，要**熟悉 根据 左闭右开，左闭右闭 两种区间规则 写出来的二分法**。



文章讲解：[https://programmercarl.com/0704.%E4%BA%8C%E5%88%86%E6%9F%A5%E6%89%BE.html](https://programmercarl.com/0704.二分查找.html)

视频讲解：https://www.bilibili.com/video/BV1fA4y1o715



704. Binary Search

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search `target` in `nums`. If `target` exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

 

**Example 1:**

```python
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4
```

**Example 2:**

```python
Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
```

 

**Constraints:**

- `1 <= nums.length <= 104`
- `-104 < nums[i], target < 104`
- All the integers in `nums` are **unique**.
- `nums` is sorted in ascending order.



**因为是排好序+无重复元素**的，所以可以考虑二分法， 左闭右开 右闭左开 没有很注意这两个方法



#####  **27. 移除元素**



**题目建议**： 暴力的解法，可以锻炼一下我们的代码实现能力，建议先把暴力写法写一遍。 **双指针法 是本题的精髓，今日需要掌握**，至于拓展题目可以先不看。 



题目链接：https://leetcode.cn/problems/remove-element/ 

文章讲解：[https://programmercarl.com/0027.%E7%A7%BB%E9%99%A4%E5%85%83%E7%B4%A0.html](https://programmercarl.com/0027.移除元素.html)

视频讲解：https://www.bilibili.com/video/BV12A4y1Z7LP 

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in `nums` [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm). The order of the elements may be changed. Then return *the number of elements in* `nums` *which are not equal to* `val`.

Consider the number of elements in `nums` which are not equal to `val` be `k`, to get accepted, you need to do the following things:

- Change the array `nums` such that the first `k` elements of `nums` contain the elements which are not equal to `val`. The remaining elements of `nums` are not important as well as the size of `nums`.
- Return `k`.

**Custom Judge:**

The judge will test your solution with the following code:

```python
int[] nums = [...]; // Input array
int val = ...; // Value to remove
int[] expectedNums = [...]; // The expected answer with correct length.
                            // It is sorted with no values equaling val.

int k = removeElement(nums, val); // Calls your implementation

assert k == expectedNums.length;
sort(nums, 0, k); // Sort the first k elements of nums
for (int i = 0; i < actualLength; i++) {
    assert nums[i] == expectedNums[i];
}
```

If all assertions pass, then your solution will be **accepted**.

 

**Example 1:**

```python
Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

**Example 2:**

```python
Input: nums = [0,1,2,2,3,0,4,2], val = 2
Output: 5, nums = [0,1,4,0,3,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.
Note that the five elements can be returned in any order.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

 

**Constraints:**

- `0 <= nums.length <= 100`
- `0 <= nums[i] <= 50`
- `0 <= val <= 100`



双指针忘光光了orz，答案写的很好





### Day 2

#####  **977.有序数组的平方** 

**题目建议**： 本题关键在于理解双指针思想 



文章讲解：

[https://programmercarl.com/0977.%E6%9C%89%E5%BA%8F%E6%95%B0%E7%BB%84%E7%9A%84%E5%B9%B3%E6%96%B9.html](https://programmercarl.com/0977.有序数组的平方.html)

视频讲解： https://www.bilibili.com/video/BV1QB4y1D7ep 



直接用内置函数 sorted很快做出来了， 但是自己做sort卡住了

------

数组其实是有序的， 只不过负数平方之后可能成为最大数了。

那么数组平方的最大值就在数组的两端，不是最左边就是最右边，不可能是中间。

此时可以考虑双指针法了，i指向起始位置，j指向终止位置。

------



#####  **209.长度最小的子数组**



**题目建议**： 本题关键在于理解滑动窗口，这个滑动窗口看文字讲解 还挺难理解的，建议大家先看视频讲解。 拓展题目可以先不做。 



题目链接：https://leetcode.cn/problems/minimum-size-subarray-sum/

文章讲解：

[https://programmercarl.com/0209.%E9%95%BF%E5%BA%A6%E6%9C%80%E5%B0%8F%E7%9A%84%E5%AD%90%E6%95%B0%E7%BB%84.html](https://programmercarl.com/0209.长度最小的子数组.html)

视频讲解：https://www.bilibili.com/video/BV1tZ4y1q7XE



做出了暴力解法$O(n^2)$， 但是TLE

------

两个for-loop一般都能用滑动窗口

------





#####  **59.螺旋矩阵II**



**题目建议**： 本题关键还是在转圈的逻辑，在二分搜索中提到的区间定义，在这里又用上了。 



文章讲解：[https://programmercarl.com/0059.%E8%9E%BA%E6%97%8B%E7%9F%A9%E9%98%B5II.html](https://programmercarl.com/0059.螺旋矩阵II.html)

视频讲解：https://www.bilibili.com/video/BV1SL4y1N7mV/



卡住了，一遇到转圈的问题就不知所措orz

------

对边处理的规则要统一，eg：左闭右开

- 起始位置 x, y每次循环要变
- offset统计圈数
- 最多圈数是n/2
- 如果n是奇数，中间会留一个

-----



#####  **总结** - 数列 



**题目建议**：希望大家 也做一个自己 对数组专题的总结



文章链接：

[https://programmercarl.com/%E6%95%B0%E7%BB%84%E6%80%BB%E7%BB%93%E7%AF%87.html](https://programmercarl.com/数组总结篇.html) 



## 2.ListNode

### Day 3

### **链表理论基础** 



建议：了解一下链接基础，以及链表和数组的区别 



文章链接：

[https://programmercarl.com/%E9%93%BE%E8%A1%A8%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html](https://programmercarl.com/链表理论基础.html)



####  **203.移除链表元素** 



建议： 本题最关键是要理解 虚拟头结点的使用技巧，这个对链表题目很重要。



题目链接/文章讲解/视频讲解：

[https://programmercarl.com/0203.%E7%A7%BB%E9%99%A4%E9%93%BE%E8%A1%A8%E5%85%83%E7%B4%A0.html](https://programmercarl.com/0203.移除链表元素.html)



####  **707.设计链表** 



建议： 这是一道考察 链表综合操作的题目，不算容易，可以练一练 使用虚拟头结点



题目链接/文章讲解/视频讲解：

[https://programmercarl.com/0707.%E8%AE%BE%E8%AE%A1%E9%93%BE%E8%A1%A8.html](https://programmercarl.com/0707.设计链表.html)



####  **206.反转链表** 



建议先看我的视频讲解，视频讲解中对 反转链表需要注意的点讲的很清晰了，看完之后大家的疑惑基本都解决了。



题目链接/文章讲解/视频讲解：

[https://programmercarl.com/0206.%E7%BF%BB%E8%BD%AC%E9%93%BE%E8%A1%A8.html](https://programmercarl.com/0206.翻转链表.html) 

























