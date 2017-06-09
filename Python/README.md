# Python

## 1. "hello, world"

### 1.1 Python interpreter
```python
>>> print("hello, world")
hello, world
```

### 1.2 File hello.py
```python
print("hello, world")
```
```
python hello.py
hello, world
```

## 2. 历史
* 发行 1991
* 作者 Guido van  Rossum(吉多 范罗苏姆 荷兰)
* ![](Guido_van_Rossum_OSCON_2006.jpg)
* 设计初衷 

    * 1989年 打发圣诞节前后的时间
    * 1999年 简单直观

        - 简单直观，与竞争者一样强大 
        - 开源，任何人可做贡献
        - 代码像纯英文
        - 适用短期开发


## 3. 编程范型
* 面向对象
* 指令式
* 函数式

## 4. 语言特性
* 明确 

## 5. 数据类型
* 动态强类型

### 布尔
### 字符串
### 数字
### 浮点
### 列表
* list 0 开始
### 字典
### None

## 6. 操作符／表达式

## 7. 流程控制

### 7.1 分支

#### 7.1.1 if
```
people = 20
cats = 30

if people < cats:
    print "Too many cats! The world is doomed!"
```

#### 7.1.2 if-else
```
people = 30
cars = 40

if cars > people:
    print "We should take the cars."
elif cars < people:
    print "We should not take the cars."
else:
    print "We can't decide."
```

### 7.2 循环
```
the_count = [1, 2, 3, 4, 5]
for number in the_count:
    print "This is count %d" % number
```
```
i = 0
numbers = []

while i < 6:
    print "At the top i is %d" % i
    numbers.append(i)

    i = i + 1
    print "Numbers now: ", numbers
    print "At the bottom i is %d" % i
```

## 8. 函数／模块

## 9. 库相关

## 10. 黑魔法

