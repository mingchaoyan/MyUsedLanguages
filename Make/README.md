# Make

## 2. 历史
* 发行 1977
* 作者 斯图亚特·费尔德曼
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/Make/stuart_feldman.jpg)
* 设计初衷 批量执行生成目标的命令，并且可以完成依赖关系的检查

## 5. 变量
类似于C语言的宏，在取值时使用$(variant)
```
objects = main.o kbd.o command.o display.o \
     insert.o search.o files.o utils.o
edit : $(objects)
    cc -o edit $(objects)
clean :
    rm edit $(objects)
```
* ``$<`` 所有依赖
* ``$@`` 所有目标

## 6. 操作符
* ``=`` 赋值
* ``:=`` 前面的变量不能使用后面的变量，只能使用前面已经定义好了的变量
* ``?=`` 如果没有被定义过，那么变量就是赋值，如果先前已经被定义过，那么这条语句将啥都不做
* ``+=`` 追加变量
* ``@`` 放在命令前，这个命令本身就不被make显示出来

## 7. 流程控制

### 7.1 总体框架
```
target ... : prerequisites ...
    command
    ...
    ...
```
* target
可以是一个object file（目标文件），也可以是一个执行文件，还可以是一个标签（label）。
* prerequisites
生成该target所依赖的文件和/或target
* command
该target要执行的命令（任意的shell命令）

### 7.2 条件判断
``` 
libs_for_gcc = -lgnu
normal_libs =

ifeq ($(CC),gcc)
    libs=$(libs_for_gcc)
else
    libs=$(normal_libs)
endif

foo: $(objects)
    $(CC) -o foo $(objects) $(libs)
```

## 8. 模块
```
include foo.make *.mk $(bar)
```

## 10. 黑魔法
* ``-`` 让make 不理会报错
