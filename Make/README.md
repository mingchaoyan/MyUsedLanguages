# Make

## 1. 历史
* 发行 1977
* 作者 斯图亚特·费尔德曼
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/Make/stuart_feldman.jpg)
* 设计初衷 批量执行生成目标的命令，并且可以完成依赖关系的检查

## 4. 变量
类似于C语言的宏，在取值时使用$(variant)
```
objects = main.o kbd.o command.o display.o \
     insert.o search.o files.o utils.o
edit : $(objects)
    cc -o edit $(objects)
clean :
    rm edit $(objects)
```

## 6. 流程控制

### 6.1 总体框架
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

### 6.2 条件判断
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

## 7. 模块
```
include foo.make *.mk $(bar)
```

## 8. 黑魔法
* ``-`` 让make 不理会报错
