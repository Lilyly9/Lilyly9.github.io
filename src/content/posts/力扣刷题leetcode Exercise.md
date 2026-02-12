---
title: 力扣Leetcode Exercise
published: 2026-01-20
description: 一轮leetcode刷题记录
tags: [ Learning ]
category: note
draft: false
---

- [数组](#数组)
  - [快慢指针](#slowfast) 
  - [滑动窗口](#滑动窗口)
-

> ## 2026

### 1.23

## 数组
<span id="数组"></span>

- [x] [***704. 二分查找***](https://leetcode.cn/problems/binary-search/)

  关于 <mark>**>=/medal±1**</mark> 的判断

  关于能取到的范围, target 所在范围：
    - 若 [left,right]，则 right 初始化为len-1， `while(left<=right)`； media > target 时，right = media-1；media < target
      时，left = media + 1
        - 若 [left,right)，则 right 初始化为 **len**，`while(left<right)`； media > target 时，right = <mark>media</mark>；media < target 时，left = media + 1
- [x] [59. 螺旋矩阵II](https://leetcode.cn/problems/spiral-matrix-ii/description/)
    <br>关于边界条件、循环不变式的确定。
  - [x] [54. 螺旋矩阵](https://leetcode.cn/problems/spiral-matrix/description/)
    1. _**避免单行/列重复遍历**_
    2. 按层遍历，收缩边界
---
### 快慢指针
<span id="slowfast"></span>

- [x] [***27. 移除元素***](https://leetcode.cn/problems/remove-element/)

    1. <mark>**快慢指针**</mark>  O(n)

       slow代表下标， fast代表查询到的元素。遍历 fast 到 len
    2. ***相对指针***

       最开始的思路，left指针检测当前 nums[left] == val，

        1. 如果是，就把 right 的值覆盖
        2. 如果不是，就后移

       **在最开始和每一次覆盖之后**，把所有 nums[right] == val 的值排除掉

*<u>while(**大循环**){ while(**小循环**)每次把特殊情况处理完 }</u>*

- [x] [***26. 删除有序数组中的重复项***](https://leetcode.cn/problems/remove-duplicates-from-sorted-array/)
- [x] [844. 比较含退格的字符串](https://leetcode.cn/problems/backspace-string-compare/solutions/683776/shuang-zhi-zhen-bi-jiao-han-tui-ge-de-zi-8fn8/)
  最后的比较需要优化 / stack方法

- [x] [***283. 移动零***](https://leetcode.cn/problems/move-zeroes/)
  只遍历一遍数组

- [x] [***997.有序数组的平方***](https://leetcode.cn/problems/squares-of-a-sorted-array/)  此题争议较大（原数组上怎么实现）

---

### 滑动窗口
<span id="滑动窗口"></span>
找**连续**字串、数组的最小/最好字串、子数组

暴力解法会把数组嵌套遍历两遍，时间复杂度O(n^2);<br>
滑动窗口的思想是直接把数组遍历两遍，时间复杂度O(2n)

- [x] [3. 无重复字符的最长子串](https://leetcode.cn/problems/longest-substring-without-repeating-characters/description/)
  HashMap存储区间内字母所在的位置；<br>
  对于每次检测的字符:
    1. 存在区间内 (idx>l)，把 l更新为idx+1
    2. 不存在区间内，不含重复字符的数组长度 length++
- [x] [904. 水果成篮](https://leetcode.cn/problems/fruit-into-baskets/description/)
  <br>含有1/2个不同数字的 最长连续子数组 长度。
- [x] [209. 长度最小的子数组](https://leetcode.cn/problems/minimum-size-subarray-sum/)
  每一轮迭代，将 nums[r] 加到sum，如果 sum ≥ target，则更新 l，更新子数组的最小长度，l不断右移到 sum<target

<style>
    mark {
        background-color: #b5627d;  
        color: #2d3748;  
        padding: 0 2px; 
        border-radius: 2px;  
        }
        
        @media (prefers-color-scheme: dark) {
        mark {
        background-color: #BB8FCE;  
        color: #333333;  
        }
    }
</style>