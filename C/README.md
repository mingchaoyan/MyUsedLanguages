# C

## 1. "hello, world"

    #include <stdio.h>
    main() 
    {
      printf("hello, world\n");
    }

## 2. 历史
* 发行 1972
* 作者 丹尼斯·里奇（Dennis Ritchie）和肯·汤普逊（Ken Thompson）
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/C/Ken_n_dennis.jpg)
* 设计初衷 移植和开发Unix

## 3. 编程范型
* 指令式
* 结构化

## 4. 语言特性
* 简洁 (32个关键字)
* 高效
* 可移植
* 静态弱类型

## 5. 数据类型
* 静态

### 5.1 基本类型
1. char
2. int
3. float
4. double
(short,long,signed,unsigned都只是限定符)

### 5.2 复杂类型

## 6. 操作符／表达式
```
1. 括号/逗号
() , 
2. 正负符号
+ - 
3. 成员
[] -> .
4. 算术
+ - * / % ++ --
5. 逻辑
! && ||
6 关系
< <= > >= == !=
7 赋值
= += -= *= /= %= &= ^= |= <<= >>=
8. 位
~ & | ^  >> <<
9. 指针
* &
10 类型
(type) sizeof
11 三元
?:
```

## 7. 流程控制

### 7.1 分支

#### 7.1.1 if-else
```C
if (a > b)
    z = a;
else
    z = b;
```

#### 7.1.2 else-if
```C
if (x < v[mid])
    high = mid - 1;
else if (x > v[mid])
    high = mid + 1
else 
    return mid;
```

#### 7.1.3 switch
```C
switch(c) {
  case '0':
    printf("zero\n");
    break;
  case '1':
    printf("one\n");
    break;
  default:
    printf("nigther\n");
    break;
}
```

### 7.2 循环

#### 7.2.1 while
```C
while(fahr <= upper) {
    celsius = 5 * (fahr-32) / 9;
    printf("%d\t%d\n", fahr, celsius);
    fahr = fahr * step;
}
```

#### 7.2.2 for
```C
for(n = 0; isdigit(s[i]); i++)
    n = 10 * n + (s[i] - '0');
```

#### 7.2.3 do-while
```C
do {
    s[i++] = n % 10 + '0';
} while(n /= 10 > 0)
```

### 7.3 跳转
```C
for(i = 0; i < n; i++)
    for(j = 0; j < m ; j++)
        if (a[i] == b[j])
            goto found;
found:
    printf("found");
```

## 8. 函数／模块

### 8.2 多文件
* 头文件中接口，C文件中实现
* [编译多文件](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/C/Misc/multi_files_compile.md)

## 9. 库相关

## 10. 黑魔法
1. 常量表达式的值在编译的时候确定
