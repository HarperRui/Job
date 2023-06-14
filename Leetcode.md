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

next 搞蒙了

####  **707.设计链表** 



建议： 这是一道考察 链表综合操作的题目，不算容易，可以练一练 使用虚拟头结点



题目链接/文章讲解/视频讲解：

[https://programmercarl.com/0707.%E8%AE%BE%E8%AE%A1%E9%93%BE%E8%A1%A8.html](https://programmercarl.com/0707.设计链表.html)

While cur:

​	Cur = cur.next

总是不知道cur最后停在none还是停在最后一个节点

***是停在了None***

cur.next = ListNode(val, cur.next) debug了半天， 写成了cur.next = ListNode(val, cur.next.next)



####  **206.反转链表** 



建议先看我的视频讲解，视频讲解中对 反转链表需要注意的点讲的很清晰了，看完之后大家的疑惑基本都解决了。



题目链接/文章讲解/视频讲解：

[https://programmercarl.com/0206.%E7%BF%BB%E8%BD%AC%E9%93%BE%E8%A1%A8.html](https://programmercarl.com/0206.翻转链表.html) 



注意细节，可以用tmp储存数据

tmp = cur

cur.next 改变了之后，原来的tmp也会变，所以要tmp储存 cur.next而不是cur





### Day 4

### 

#### **24. 两两交换链表中的节点** 

用虚拟头结点，这样会方便很多。 



本题链表操作就比较复杂了，建议大家先看视频，视频里我讲解了注意事项，为什么需要temp保存临时节点。



题目链接/文章讲解/视频讲解： [https://programmercarl.com/0024.%E4%B8%A4%E4%B8%A4%E4%BA%A4%E6%8D%A2%E9%93%BE%E8%A1%A8%E4%B8%AD%E7%9A%84%E8%8A%82%E7%82%B9.html](https://programmercarl.com/0024.两两交换链表中的节点.html)

边界条件自己想错了，整个思路想出来了。 Dummy忘记用了



####  **19.删除链表的倒数第N个节点** 



双指针的操作，要注意，删除第N个节点，那么我们当前遍历的指针一定要指向 第N个节点的前一个节点，建议先看视频。



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0019.%E5%88%A0%E9%99%A4%E9%93%BE%E8%A1%A8%E7%9A%84%E5%80%92%E6%95%B0%E7%AC%ACN%E4%B8%AA%E8%8A%82%E7%82%B9.html](https://programmercarl.com/0019.删除链表的倒数第N个节点.html)



两指针相差n+1有点卡，一开始用的是n



#### **面试题 02.07. 链表相交** 

本题没有视频讲解，大家注意 数值相同，不代表指针相同。



题目链接/文章讲解：[https://programmercarl.com/%E9%9D%A2%E8%AF%95%E9%A2%9802.07.%E9%93%BE%E8%A1%A8%E7%9B%B8%E4%BA%A4.html](https://programmercarl.com/面试题02.07.链表相交.html)

没有思路，不知道后面对齐就可以了。



#### **142.环形链表II** 



算是链表比较有难度的题目，需要多花点时间理解 确定环和找环入口，建议先看视频。



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0142.%E7%8E%AF%E5%BD%A2%E9%93%BE%E8%A1%A8II.html](https://programmercarl.com/0142.环形链表II.html)

思路好难，还有数学推导



## 3.Hashtable

### Day 6



###  **哈希表理论基础** 



建议：大家要了解哈希表的内部实现原理，哈希函数，哈希碰撞，以及常见哈希表的区别，数组，set 和map。 



什么时候想到用哈希法，**当我们遇到了要快速判断一个元素是否出现集合里的时候，就要考虑哈希法**。 这句话很重要，大家在做哈希表题目都要思考这句话。 



文章讲解：[https://programmercarl.com/%E5%93%88%E5%B8%8C%E8%A1%A8%E7%90%86%E8%AE%BA%E5%9F%BA%E7%A1%80.html](https://programmercarl.com/哈希表理论基础.html)  



####  **242.有效的字母异位词**  



建议： 这道题目，大家可以感受到 数组 用来做哈希表 给我们带来的遍历之处。 



题目链接/文章讲解/视频讲解： [https://programmercarl.com/0242.%E6%9C%89%E6%95%88%E7%9A%84%E5%AD%97%E6%AF%8D%E5%BC%82%E4%BD%8D%E8%AF%8D.html](https://programmercarl.com/0242.有效的字母异位词.html)  

不难



####  **349. 两个数组的交集** 



建议：本题就开始考虑 什么时候用set 什么时候用数组，本题其实是使用set的好题，但是后来力扣改了题目描述和 测试用例，添加了 0 <= nums1[i], nums2[i] <= 1000 条件，所以使用数组也可以了，不过建议大家忽略这个条件。 尝试去使用set。 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0349.%E4%B8%A4%E4%B8%AA%E6%95%B0%E7%BB%84%E7%9A%84%E4%BA%A4%E9%9B%86.html](https://programmercarl.com/0349.两个数组的交集.html)  

不难, 因为最后返回的是unique value，所以可以考虑用set



####  **202. 快乐数** 



建议：这道题目也是set的应用，其实和上一题差不多，就是 套在快乐数一个壳子 



题目链接/文章讲解：[https://programmercarl.com/0202.%E5%BF%AB%E4%B9%90%E6%95%B0.html](https://programmercarl.com/0202.快乐数.html)  

求每个位置的digit有点卡住了

"如果中间结果重复出现，说明陷入死循环了，该数不是快乐数" 这个没想到



#### 1. 两数之和



建议：本题虽然是 力扣第一题，但是还是挺难的，也是 代码随想录中 数组，set之后，使用map解决哈希问题的第一题。 



建议大家先看视频讲解，然后尝试自己写代码，在看文章讲解，加深印象。 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0001.%E4%B8%A4%E6%95%B0%E4%B9%8B%E5%92%8C.html](https://programmercarl.com/0001.两数之和.html) 

不难



### Day 7



#### **454.四数相加II** 



建议：本题是 使用map 巧妙解决的问题，好好体会一下 哈希法 如何提高程序执行效率，降低时间复杂度，当然使用哈希法 会提高空间复杂度，但一般来说我们都是舍空间 换时间， 工业开发也是这样。



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0454.%E5%9B%9B%E6%95%B0%E7%9B%B8%E5%8A%A0II.html](https://programmercarl.com/0454.四数相加II.html)  



没有思路，但是感觉像是2sum的变形

!!!实际上和3sum， 4sum不一样， 因为这个题的结果不用去重



####  **383. 赎金信** 



建议：本题 和 242.有效的字母异位词 是一个思路 ，算是拓展题 



题目链接/文章讲解：[https://programmercarl.com/0383.%E8%B5%8E%E9%87%91%E4%BF%A1.html](https://programmercarl.com/0383.赎金信.html) 

不难



####  **15. 三数之和** 



建议：本题虽然和 两数之和 很像，也能用哈希法，但用哈希法会很麻烦，双指针法才是正解，可以先看视频理解一下 双指针法的思路，文章中讲解的，没问题 哈希法很麻烦。 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0015.%E4%B8%89%E6%95%B0%E4%B9%8B%E5%92%8C.html](https://programmercarl.com/0015.三数之和.html) 

双指针，重点是去重，用set不行（因为list是unhashble, 但是可以用tuple(list)）



####  **18. 四数之和** 



建议： 要比较一下，本题和 454.四数相加II 的区别，为什么 454.四数相加II 会简单很多，这个想明白了，对本题理解就深刻了。 本题 思路整体和 三数之和一样的，都是双指针，但写的时候 有很多小细节，需要注意，建议先看视频。 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0018.%E5%9B%9B%E6%95%B0%E4%B9%8B%E5%92%8C.html](https://programmercarl.com/0018.四数之和.html) 



和3sum很像

## 4. String

### Day 8 

#### **344.反转字符串** 



建议： 本题是字符串基础题目，就是考察 reverse 函数的实现，同时也明确一下 平时刷题什么时候用 库函数，什么时候 不用库函数 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0344.%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2.html](https://programmercarl.com/0344.反转字符串.html)  



####  **541. 反转字符串II**



建议：本题又进阶了，自己先去独立做一做，然后在看题解，对代码技巧会有很深的体会。 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0541.%E5%8F%8D%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2II.html](https://programmercarl.com/0541.反转字符串II.html)  





####  **剑指Offer 05.替换空格** 



建议：对于线性数据结构，填充或者删除，后序处理会高效的多。好好体会一下。

题目链接/文章讲解：[https://programmercarl.com/%E5%89%91%E6%8C%87Offer05.%E6%9B%BF%E6%8D%A2%E7%A9%BA%E6%A0%BC.html](https://programmercarl.com/剑指Offer05.替换空格.html)  





####  **151.翻转字符串里的单词** 



建议：这道题目基本把 刚刚做过的字符串操作 都覆盖了，不过就算知道解题思路，本题代码并不容易写，要多练一练。 



题目链接/文章讲解/视频讲解：[https://programmercarl.com/0151.%E7%BF%BB%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2%E9%87%8C%E7%9A%84%E5%8D%95%E8%AF%8D.html](https://programmercarl.com/0151.翻转字符串里的单词.html)  



####  **剑指Offer58-II.左旋转字符串** 



建议：题解中的解法如果没接触过的话，应该会想不到



题目链接/文章讲解：[https://programmercarl.com/%E5%89%91%E6%8C%87Offer58-II.%E5%B7%A6%E6%97%8B%E8%BD%AC%E5%AD%97%E7%AC%A6%E4%B8%B2.html](https://programmercarl.com/剑指Offer58-II.左旋转字符串.html)  
