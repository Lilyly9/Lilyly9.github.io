---
title: 力扣刷题Leetcode Exercise
published: 2026-01-20
tags: [Learning]
category: note
draft: false
---
## ***2026***
### ***1.23***

- [x] 二分查找 704

  关于 <mark>**>=/medal±1**</mark> 的判断

  关于能取到的范围, target 所在范围：
    - 若 [left,right]，则 right 初始化为len-1， `while(left<=right)`； media > target 时，right = media-1；media < target 时，left = media + 1
        - 若 [left,right)，则 right 初始化为 **len**，`while(left<right)`； media > target 时，right = <mark>__media__</mark>；media < target 时，left = media + 1
---
- [ ] 移除元素 27

    1. **快慢指针**  O(n)

       slow代表下标， fast代表查询到的元素。遍历 fast 到 len
    2. 相对指针

---
- [ ] 


<style>
    mark {
        background-color: #fef3c7; /* 柔和的浅黄色（不刺眼） */
        color: #2d3748; /* 文字颜色 */
        padding: 0 2px; /* 左右内边距，避免文字贴边 */
        border-radius: 2px; /* 轻微圆角，更优雅 */
        }
        
        /* 深色模式适配 */
        @media (prefers-color-scheme: dark) {
        mark {
        background-color: #44403c; /* 深色模式下的浅棕色 */
        color: #f5f5f4; /* 浅色文字 */
        }
    }
</style>