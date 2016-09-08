# Erlang

## 0. hello, world
```erlang
-module(hello).
-export([hello_world/0]).
hello_world() ->
    io:fwrite("hello, world\n")
```

## 1. 历史
* 发行:1987
* 作者:乔·阿姆斯特朗，麦可·威廉， 罗伯·维丁 
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/Erlang/Erlang-1987.jpg)
* 设计初衷 电信设备制造商爱立信私有软件，创造一个种可以应付大规模开发活动的程序设计语言和运行环境

## 2. 编程范型
* 函数式
* 并发

## 3. 语言特性
* 并发
* 无锁/函数式
* 消息通信
* 容错/热更新


## 4. 数据类型
* 动态强类型

##### 基本类型
1. 原子(包括布尔类型): far, true, false
2. 整数:42
3. 浮点数:3.14
4. 二进制
5. func
6. pid
7. port
8. ref

##### 复合类型
9. list/string
* 以1开始
10. tuple/record

## 5. 运算操作

## 6. 流程控制

* 分支

```erlang

```
* 循环

```erlang

```

## 7. 函数／模块
### 7.1 包管理器
rebar
