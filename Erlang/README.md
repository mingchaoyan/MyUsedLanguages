# Erlang

## 1. "hello, world"

### 1.1 Erlang shell

    $ erl
    Erlang/OTP 19 [erts-8.1] [source] [64-bit] [smp:4:4] [async-threads:10] [hipe] [kernel-poll:false] [dtrace]

    Eshell V8.1  (abort with ^G)
    1> io:format("hello, world\n").
    hello, world
    ok
    2> q().
    ok
    3> $

### 1.2 Script
* 编辑 

    #! /usr/bin/env escript
    main(_) ->
        io:format("hello, world\n").

* 解释运行

    $ chmod +x hello.erl
    $ ./hello.erl
    hello, world

### 1.3 Compile
* 编辑 

    -module(hello).
    -export([hello_world/0]).
    hello_world() ->
        io:fwrite("hello, world\n").

* 编译产生beam文件
```shell
$ erlc hello.erl 
$ ls 
$ hello.beam
```
* 运行erl 载入beam文件
```shell
$ erl
> hello:hello_world().
> hello, world
```

## 2. 历史
* 发行：1986
* 作者：乔·阿姆斯特朗（瑞典），罗伯·维丁（瑞典），麦可·威廉（瑞典）
* <img src="Erlang-1987.jpg" width="50%" height="50%">
* 设计初衷：电信设备制造商爱立信私有软件，创造一种可以应付大规模并发活动的程序设计语言和运行环境

## 3. 编程范型
* 函数式
* 并发

## 4. 语言特性
* 并发
* 无锁/函数式
* 消息通信
* 容错/热更新


## 5. 数据类型
* 动态强类型

### 5.1 基本类型
1. 原子(包括布尔类型): far, true, false
2. 整数:42
3. 浮点数:3.14
4. 二进制
5. func
6. pid
7. port
8. ref

### 5.2复合类型
9. list/string
* 以1开始
10. tuple/record

## 6. 运算操作

## 7. 流程控制

* 分支

```erlang

```
* 循环

```erlang

```

## 8. 函数／模块

## 9. 库相关

### 9.1 包管理器
hex.pm

### 9.2 集成测试
eunit

