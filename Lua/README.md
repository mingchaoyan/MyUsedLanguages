# Lua

## 1. "hello, world"

### 1.1 Lua interpreter
    
    $ lua
    Lua 5.3.3  Copyright (C) 1994-2016 Lua.org, PUC-Rio
    > print("Hello, World")
    Hello World
    > os.exit()
    $

### 1.2 Script
* 编辑

    ```lua
    #! /usr/bin/env lua
    print("Hello, World")
    ```

* 解释运行

    $ chmod +x hello.lua
    $ ./hello.lua
    Hello, World

### 1.3 File hello.lua
* 编辑

    print("Hello, World")

* 解释运行

    lua hello.lua


## 2. 历史
* 发行 1993
* 作者 Roberto Ierusalimschy (巴西)
       Waldemar Celes (巴西)
       Luiz Henrique de Figueiredo (巴西)
* ![](lua.jpg)
* 设计初衷 成为一个很容易嵌入其它语言中使用的语言

## 3. 编程范型
* 基于原型
* 面向对象
* 过程式(命令式)
* 函数式

## 4. 语言特性
* 轻量

## 5. 数据类型
* 动态弱类型

### 5.1 nil
### 5.2 布尔 boolean
### 5.3 数字 number
### 5.4 字符串 string
### 5.5 函数 function
### 5.6 线程 thread
### 5.7 表 table
* 数组以1开始
* a.field 是 a['field'] 的语法糖
### 5.8 用户自定义 userdata

## 6. 操作符／表达式
### 6.1 数学操作符
* +
* -
* *
* /
* %
* -
* ^

### 6.2 比较操作符
* ==
* ~=
* <
* >
* /</=
* />/=

### 6.3 逻辑操作符
* not
* and
* or

### 6.4 连接操作符
* ...

### 6.5 取长度操作符
* #

## 7. 流程控制

### 7.1 分支

#### 7.1.1 if-else
```
if xxx then
    xxx
elseif xxx then
    xxx
else
    xxx
end
```

### 7.2 循环
#### 7.2.1 while
#### 7.2.2 repeat 
#### 7.2.3 for

## 8. 函数／模块
### 8.1 require 的加载过程
* 查看package.loaded 是否已经被加载
* 通过模块名找相应的lua文件 使用loadfile("luafilename.lua") 获取一个函数，成为loader
* 没有lua模块就找c模块，loadlib的结果作为loader
* require 调用loader这个函数，把return的结果存放在package.loaded
### 8.2 模块的两种写法
```lua
local M = {}
function M.new() 
  return xxx
end
return M
```
```lua
local function new()
    return xxx
end
rerurn {
    new = new
}
```
### 8.3 包(package)
* lua 会把代码中的 ``.`` 转换成路径分隔符
```
require "a.b"
```

## 9. 库相关

### 9.1 包管理
luarock

### 9.2 集成测试
busted

### 9.3 table pretty
inspect

## 10. 黑魔法
* 多值赋值，多值返回
```
x, y = y, x -- swap
```
* 函数参数如果只有一个并且是字符串或者table，函数的参数括号可以省略
* metatable
重新定义table的行为，通俗的可以理解为预定义操作符的重载
* path
* assert

