# Q

## 1. "hello, world"

    TracePrint "hello world"

## 2. 历史
* 发行 2001 按键精灵 1.0 
* 作者 按键精灵团队
* 设计初衷 让使用者以最简洁的语言对电脑发号施令，让人不再做电脑的奴隶

## 3. 编程范型

## 4. 语言特性

## 5. 数据类型
* 动态弱类型
### 5.1 数值类型
* Int
* Long
* Single
* Double

### 5.2 字符串类型

    "你好"

### 5.3 布尔类型

* True
* False

### 5.4 货币类型

### 5.5 数值
```
Dim a(n) 
```
* 下标 0 开始，最大到 n
* a(i, j)


## 6. 操作符／表达式

### 6.1 算术运算
```
+
-
*
/
Mod
^
\
 ```

### 6.2 关系运算
```
=
>
<
>=
<=
<>
```

### 6.3 逻辑运算
```
And
Or
Not
Eqv
Xor
Imp
```

## 7. 流程控制

### 7.1 分支

#### 7.1.1 if
* if-then
```
if intX > 0 Then MoveTo 100, 100
```

```
If intX > 0 Then
    MoveTo 100, 100
    Delay 200
    LeftClick 1
End If
```

* if-then-else
```
If intX > 0 Then
    TracePint "intX 坐标大于 0"
Else
    TracePrint "intX 坐标小于 0"
End If
```

* if-then-elseif
```
If HP > 80 Annd HP < 90 Then
// 使用小瓶红药
ElseIf HP > 60 And HP < 80 Then
// 使用中瓶红药
ElseIf HP > 0 And HP < 60 Then
// 使用大瓶红药
End If
```

#### 7.1.2 IfColor
```
IfColor 1289, 281, "B9A05E" Then
    MessageBox "颜色等于"
Else
    MessageBox "颜色不等于"
End If
```

#### 7.1.3 Select Case
```
UserVar server_name = 1 "Input Server Name"
Select Case server_name
	Case 1
		MessageBox "your server is 1"
	Case 2
		MessageBox "your server is 2"
	Case Else
		MessageBox "No such server"
End Select
```

### 7.2 循环

#### 7.2.1 for 

```
For 3
    KeyPress "A" , 1
Next
```
```
For i = 1 To 3 Step 1
    KeyPress "A", 1
Next
```
* 使用 Exit For 跳出循环

#### 7.2.2 do-loop
```
a = 1
Do While a = 1
    LeftClick 1
Loop 
```
```
a = 0
Do Until a = 1 // 表达式为假执行循环体
    MessageBox 1
Loop
```
```
a = 0
Do 
    MessageBox "a=" & a
    a = a + 1
Loop While a < 3
```
```
a = 0
Do
    MessageBox "a=" & a
    a = a + 1
Loop Until a < 3
```
```
a = 1
while a < 10
    MessageBox a
    a = a + 1
Wend
```

### 7.3 跳转

## 8. 函数／模块

* 函数和子过程唯一区别：函数有返回值，子过程没有

### 8.1 子程序
```
Call auto_heal()
TracePrint "call auto_heal complete"
Sub auto_heal()
    IfColor 1289, 281, "B9A05E", 0 Then
        MessageBox "颜色等于"
    Else
        MessageBox "颜色不等于"
    End If
End Sub
```

### 8.2 函数
```
sum = add(1, 2)
TracePrint "1+2=" & sum
Function sum(a, b)
    sum = a + 1
End Funnction
```

## 9. 库相关

## 10. 黑魔法

