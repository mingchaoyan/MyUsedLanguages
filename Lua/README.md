# Lua

## 0. "hello, world"
* Lua interpreter
```
> print("Hello, World")
```

* File hello.lua
```
print("Hello, World")
```
```shell
lua hello.lua
```

## 1. 历史
* 发行 1993
* 作者 Roberto Ierusalimschy 
       Waldemar Celes
       Luiz Henrique de Figueiredo
* ![](lua.jpg)
* 设计初衷 成为一个很容易嵌入其它语言中使用的语言

## 2. 编程范型
* 基于原型
* 面向对象
* 过程式(命令式)
* 函数式

## 3. 语言特性
* 轻量

## 4. 数据类型
* 动态弱类型

### 4.1 nil
### 4.2 布尔 boolean
### 4.3 数字 number
### 4.4 字符串 string
### 4.5 函数 function
### 4.6 线程 thread
### 4.7 表 table
* 数组以1开始
* a.field 是 a['field'] 的语法糖
### 4.8 用户自定义 userdata

## 5. 操作符／表达式
### 5.1 数学操作符
* +
* -
* *
* /
* %
* -
* ^

### 5.2 比较操作符
* ==
* ~=
* <
* >
* /</=
* />/=

### 5.3 逻辑操作符
* not
* and
* or

### 5.4 连接操作符
* ...

### 5.5 取长度操作符
* #

## 6. 流程控制

### 6.1 分支

#### 6.1.1 if-else
```
if xxx then
    xxx
elseif xxx then
    xxx
else
    xxx
end
```

### 6.2 循环
#### 6.2.1 while
#### 6.2.2 repeat 
#### 6.2.3 for

## 7. 函数／模块
### 7.1 require 的加载过程
* 查看package.loaded 是否已经被加载
* 通过模块名找相应的lua文件 使用loadfile("luafilename.lua") 获取一个函数，成为loader
* 没有lua模块就找c模块，loadlib的结果作为loader
* require 调用loader这个函数，把return的结果存放在package.loaded
### 7.2 模块的两种写法
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
### 7.3 包(package)
* lua 会把代码中的 ``.`` 转换成路径分隔符
```
require "a.b"
```
## 8. 库相关

## 9. 黑魔法
* 多值赋值，多值返回
```
x, y = y, x -- swap
```
* 函数参数如果只有一个并且是字符串或者table，函数的参数括号可以省略


