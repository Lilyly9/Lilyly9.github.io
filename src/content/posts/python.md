---
title: python
published: 2026-02-28
description: "python基础语法"
image: ''
tags: [Learn]
category: 'note'
draft: false
---
- [python基础](#python基础)
    - [注释](#注释)
    - [字符串与字符串连接](#字符串与字符串连接)
    - [数据类型](#数据类型)
    - [输入 input](#输入-input)
    - [条件判断语句](#条件判断语句)
    - [循环语句](#循环语句)
    - [逻辑运算](#逻辑运算)
    - [列表 List](#列表-list)
    - [元组 Tuple](#元组-tuple)
    - [集合 Set](#集合-set)
    - [字典 {}](#字典-)
- [模块](#模块)
- [类 \& 方法](#类--方法)
  - [继承](#继承)
  - [属性封装\&property](#属性封装property)

# python基础
### 注释
#/三引号"""……""" 多行注释
### 字符串与字符串连接
1. 字符串连接 +
   ```python
   print("Hello"+"World"+"!")
   ```
2. 双单引号转义
   ```python
    print('He said "good!"') # 单引号包裹 He said "good"
    print("He said 'good!'") # 双引号包裹 He said 'good'
    print("He said \"Let's go!\"") # 转义符 He said "Let's go!"
   ```
3. 三引号跨行字符串
   自换行
   ```python
   print("""Hello
   World""")
   ```
4. 常用方法
   ```python
    s = "hello"
    s.upper()    # 转大写 HELLO
    s.lower()    # 转小写
    s.strip()    # 去掉首尾空格
    s.replace("h", "H")  # 替换
    s.split(",") # 按符号分割成列表
    ```
### 格式化字符串
1. format()
   ```python
   print("My name is {0},I'm {1} years old".format("Liz", 19))
    print("My name is {name},I'm {age} years old".format(name="Liz", age=19))
    name = "Yuzy"
    age = 20
    print(f"My name is {name},I'm {age} years old")
   ```
2. f-字符串

### 数据类型
1. 字符串 str
   ```python
   len("Hello") # 5
   len("哟! ") # 2
   len("\n") # 1
   ```
2. 整型 int、浮点数 float
   ```python
   grade =93.546
    print("Your grade is: " + f"{grade:.2f}") # Your grade is: 93.55
   ```
3. 布尔类型
4. **type** 输出数据类型
### 输入 input
```python
user_name = str(input("请输入用户名："))
```
### 条件判断语句
```python
grade = int(input("please input your grade: "))
if grade >= 90:
    print("A")
elif grade >= 80:
    print("B")
elif grade >= 65:
    print("C")
else:
    print("D")
```
### 循环语句
```python
constants = ("Alice", "Bob", "Charlie", "David", "Eve")
for contant in constants:
    print(contant)

for i in range(5,10):  # [5,10)
    print(i)
for i in range(5,10,2):  # 5 7 9 步长为2
    print(i)
    
i = 0
while i <len(constants):
    print(constants[i])
    i += 1
```
### 逻辑运算
```python
x = int(input("Enter a number: "))
print(not(x>5 and x<10)) # 6 -False;2 - True
```
### 列表 List
有序、可重复、可扩展
```python
shopping_list = ["milk", "eggs", "bread"]
shopping_list.append("bread") # ['milk', 'eggs', 'bread', 'bread']
shopping_list.remove("eggs") # ['milk', 'bread', 'bread']
len(shopping_list) # 3
print(shopping_list[1]) # eggs
print(shopping_list[0:2]) # ['milk', 'eggs']
print(shopping_list[0:2]) # ['milk', 'eggs']
shopping_list.insert(1, 15)  # 指定位置插入
shopping_list.pop()          # 删除最后一个
shopping_list.pop(0)         # 删除指定索引
shopping_list.clear()        # 清空
shopping_list.sort()         # 对于int排序
shopping_list.reverse()      # 反转
print(shopping_list)         # []
```
### 元组 Tuple
有序、可重复、不可扩展，当作键使用
```python
example_tuple = ("keyboard", "mouse", "monitor")
example_tuple.append("printer")  # ❌
example_tuple.remove("mouse")  # ❌
# 作为键
contacts = {
    ("Lily",19):"421880110",
    ("Bob",25):"421880111",
    ("Tom",30):"421880112"
}
print(contacts[("Lily",19)])  # 输出：421880110
```
### 集合 Set
无序、不可重复、可扩展
```python
names = {"Lily","Rose","Daisy","Iris"}
print("Lily" in names) # True
print(type(names)) # <class 'set'>
```
### 字典 {}
键 : 值
```python
contacts ={
    "Alice": "152-555-1234",
    "Bob": "152-555-5678",
}
print(contacts.get("Alice")) # 152-555-1234
print(contacts.get("Charlie")) # None
print(contacts["Alice"]) # Output: 152-555-1234
print("Bob" in contacts) # Output: True
# 删除键值对 del 字典名[键]
del contacts["Alice"]
print(len(contacts)) # Output: 1
# 遍历字典
for name in contacts:
    print(name, contacts[name])
# 所有键
print(contacts.keys()) # Output: dict_keys(['Bob'])
# 所有值    
print(contacts.values()) # Output: dict_values(['152-555-5678'])
# 所有键值对
print(contacts.items()) # Output: dict_items([('Bob', '152-555-5678')])
```
# 模块
继承很多功能的函数集合 称作模块  
```python
# 自定义模块，导入module.py中的函数
import math
print(math.sqrt(16))
# 直接调用，不加模块名
from math import *
print(sqrt(16))
print(math.sqrt(16)) # math 本身没有被导入！NameError: name 'math' is not defined

# 导入内置模块
import random
num = random.randint(1, 100)
print(num)
random_list = [11,22,33,44]
data = random.choice(random_list)
print(data)

# from 模块名 import sqrt
from math import sqrt
print(sqrt(16))

# import 模块名 as 别名
import math as m
print(m.sqrt(16))
```
# 类 & 方法
1. 基本语法
   ```python
   class Dog:
    pass
  
    my_dog = Dog()          # 创建实例（对象）
    print(type(my_dog))     # <class '__main__.Dog'>
   ```
2. 初始化方法__init__和实例属性
    <br>双下划线：私有属性
    ```python
    class Dog:
        def __init__(self, name, age):
            self.name = name   # 实例属性
            self.age = age

    my_dog = Dog("旺财", 3)
    ```
3. 魔术方法
    ```python
    class Cat:
        def __init__(self, name):
            self.name = name

        # 魔术方法：控制对象打印结果
        def __str__(self):
            return f"猫咪：{self.name}"

    tom = Cat("汤姆")
    print(tom)  # 自动执行 __str__，输出：猫咪：汤姆

    class Book:
        def __len__(self):
            return 200  # 自定义页数

    b = Book()
    print(len(b))  # 自动调用 __len__，输出 200
    ```
4. 实例方法
   ```python
    class Dog:
        def __init__(self, name, age):
            self.name = name
            self.age = age

        def get_human_age(self):
            return self.age * 7

    my_dog = Dog("旺财", 3)
    human_age = my_dog.get_human_age()  # 21
   ```
5. 类属性 vs 实例属性
    ```python
    class Dog:
        species = "Canis familiaris"   # 类属性

        def __init__(self, name):
            self.name = name            # 实例属性

    dog1 = Dog("旺财")
    dog2 = Dog("来福")
    print(dog1.species)  # Canis familiaris
    print(dog2.species)  # Canis familiaris
    print(Dog.species)  # 直接通过类名查询：Canis familiaris
    Dog.species = "狗"    # 修改类属性会影响所有实例
    print(dog1.species)  # 狗
    ```
6. 类方法
    <br>第一个参数是cls（类本身）
    ```python
    class Dog:
        total_dogs = 0

        def __init__(self, name):
            self.name = name
            Dog.total_dogs += 1

        @classmethod
        def get_total(cls):
            return cls.total_dogs

    print(Dog.get_total())  # 0
    d1 = Dog("旺财")
    d2 = Dog("来福")
    print(Dog.get_total())  # 2
    ```
7. 静态方法
   和普通函数的区别是：不能访问实例属性或类属性
    ```python
    class MathUtils:
        @staticmethod
        def add(x, y):
            return x + y

    print(MathUtils.add(3, 5))  # 8
    ```
## 继承
1. 基础格式
    ```python
    class Animal:
        ……
    class Dog(Animal):
        ……
    ```
2. ```super()```调用父类方法
   ```python
   class Cat(Animal):
    def speak(self):
        super().speak()      # 先调用父类方法
        print("喵喵喵")      # 再添加子类行为
   ```
## 属性封装&property
Python 没有严格的私有属性，但约定以 _ 开头的属性为“保护”的，不应当直接访问。可以使用```@property```提供 getter/setter。
```python
class Person:
    def __init__(self, name):
        # 私有属性，外部不直接访问
        self._name = name

    # 取值方法：对象.name 自动调用
    @property
    def name(self):
        return self._name

    # 赋值方法：对象.name = 值 自动调用
    @name.setter
    def name(self, val):
        # 简单校验
        if len(val) < 2:
            raise ValueError("名字太短")
        self._name = val

# 使用
p = Person("小明")
print(p.name)     # 调用@property，取值

p.name = "小红"    # 调用setter，赋值
print(p.name)
```