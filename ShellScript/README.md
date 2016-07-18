# ShellScript

## 0. "hello, world"
```
echo "hello, world"
```

## 1. 历史
* 发行 1975
* 作者 Ken Tompson
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/ShellScript/Ken_Tompson.jpeg)
* 设计初衷 用户向操作系统发送请求以便运行程序

## 4. 变量/数据类型
* 变量名与等号之间不能有空格
* 使用变量: 变量名前加``$``，推荐给所有变量加花括号(帮助解释器识别变量边界)
* 数据类型：字符串和数字

## 6. 流程控制

### 6.1 分支
#### 6.1.0 test 和 [ 逻辑判断
```
VAR=2
test ${VAR} -gt 1
echo $?

[ ${VAR} -gt 3 ]
echo $?
```
测试结果真为0，假为1(和C语言逻辑正好相反)

#### 6.1.1 if/then/elif/else/fi

#### 6.1.2 case/esac
* 分支结尾必须是;;
* 分支不需要使用 break 跳出

## 7. 函数／模块
* 文件包含：``source`` 或者 ``.``

## 9. 黑魔法
* ``$``符号后面的 ``{}`` 表变量的值，在不引起歧义的情况下可以省略，``()``命令替换
