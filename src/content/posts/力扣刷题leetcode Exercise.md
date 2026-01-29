---
title: 力扣刷题Leetcode Exercise
published: 2026-01-20
description: 一轮leetcode刷题记录
tags: [Learning]
category: note
draft: false
---
## 2026
### 1.23

- [x] ***二分查找 704***

  关于 <mark>**>=/medal±1**</mark> 的判断

  关于能取到的范围, target 所在范围：
    - 若 [left,right]，则 right 初始化为len-1， `while(left<=right)`； media > target 时，right = media-1；media < target 时，left = media + 1
        - 若 [left,right)，则 right 初始化为 **len**，`while(left<right)`； media > target 时，right = <mark>__media__</mark>；media < target 时，left = media + 1
---
  - [x] ***移除元素 27***

      1. <mark>**快慢指针**</mark>  O(n)

         slow代表下标， fast代表查询到的元素。遍历 fast 到 len
      2. ***相对指针***

         最开始的思路，left指针检测当前 nums[left] == val，
   
         1. 如果是，就把 right 的值覆盖
         2. 如果不是，就后移
         
         **在最开始和每一次覆盖之后**，把所有 nums[right] == val 的值排除掉

- [x] ***删除有序数组中的重复项 26***

---
- [ ] 


<style>
    mark {
        background-color: #fef3c7;  
        color: #2d3748;  
        padding: 0 2px; 
        border-radius: 2px;  
        }
        
        @media (prefers-color-scheme: dark) {
        mark {
        background-color: #44403c;  
        color: #f5f5f4;  
        }
    }
</style>