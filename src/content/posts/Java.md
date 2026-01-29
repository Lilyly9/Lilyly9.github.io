---
title: Java
published: 2026-01-28
description: 'Java学习笔记'
image: ''
tags: [Java]
category: 'Java'
draft: true
lang: ''
---

>## StringBuffer

1. 为什么需要StringBuffer？

    [**String**](#String) 是不可变的。若执行 `str = str + "a"`, JVM 会 **创建新的字符串对象**，频繁拼接会产生大量临时对象，效率极低。
    
 
   2.**StringBuffer 特性**：

      **线程安全**：所有方法都加了 `synchronized` 同步锁，多线程环境下使用不会出现数据错乱（这是它和 StringBuilder 的核心区别）；

      **可变字符序列**：支持增、删、改、插等操作，且操作后对象本身不变；
      **初始容量/自动扩容**：默认初始容量是 16 个字符，当字符数超过容量时，会自动扩容（扩容为原容量 * 2+2），扩容会有性能损耗，若能预估长度，建议手动指定初始容量。

    ```java
    StringBuffer sb = new StringBuffer(20); // 初始容量20

    sb.append("Hello");
    sb.append(" ");
    sb.append("Java");
    System.out.println("拼接后：" + sb); // 输出：Hello Java

    // 3. 插入字符/字符串（insert）
    sb.insert(5, ", World"); // 在索引5的位置插入
    System.out.println("插入后：" + sb); // 输出：Hello, World Java

    // 4. 修改指定索引的字符（setCharAt）
    sb.setCharAt(0, 'h'); // 把第一个字符改为小写h
    System.out.println("修改后：" + sb); // 输出：hello, World Java

    // 5. 删除字符（delete）
    sb.delete(5, 12); // 删除索引5到11的字符（左闭右开）
    System.out.println("删除后：" + sb); // 输出：hello Java

    // 6. 反转字符串（reverse）
    sb.reverse();
    System.out.println("反转后：" + sb); // 输出：avaJ olleh

    // 7. 转为普通 String
    String finalStr = sb.toString();
    ```
   
---












---
<span id="String"></span>
String的不可变性

- 实现原理

  ```java
   public final class String{
        private final char value[];
   }
   ```   
  1. String 类被 **final** 修饰，<u>无法被继承</u>；内部存储字符的 char[] value 数组也被 **final** 修饰，保证 <u>该数组引用不可指向新数组</u>。
  2. 数组的 **private** 封装char[] value 被 private 修饰，外部无法直接访问或修改这个数组。
  3. 无修改方法，操作返回新对象String 没有提供修改内部数组的公开方法，所有字符串操作（如拼接、替换）都会返回新的 String 对象，原对象内容不变。
- 为什么这样设计？

   字符串常量池才能发挥作用。








