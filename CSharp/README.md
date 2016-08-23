# C♯

## 0. hello, world
Hello.cs
```cs
public class Hello
{
  public static void Main()
  {
    System.Console.WriteLine("hello, world");
  }
}
```
OSX
```shell
$ mcs Hello.cs
$ mono Hello.exe
hello, world
```
## 1. 历史
* 发行:2000
* 作者:安德斯·海尔斯伯格
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/CSharp/Anders_Hejlsberg.jpg)
* 设计初衷 微软为了对抗Java
* Unity 5.x 使用Mono2.6 相当于.NET 4 （C# 4.0）

## 2. 编程范型
* 指令式
* 面向对象
* 事件驱动
* 函数式
* 范型
* 元编程

## 3. 语言特性
* 简单
* 现代
* 通用

## 4. 数据类型
* 强类型 
* 静态/动态类型

### 4.1  值类型
#### 4.1.1  数值

##### 4.1.1.1 整数
* sbyte / byte  1
* short / ushort    2
* int / uint    4
* long / ulong  8

##### 4.1.1.2 浮点数
* float 4
* double 8

#### 4.1.2 字符
* char 2

#### 4.1.3 布尔
#### 4.1.4  枚举
```
enum Color {
    Red,
    Green,
    Blue
}
```
#### 4.1.6 结构
* 和C++最大的不同是C#中结构体是值类型

### 4.2 引用类型

#### 4.2.1 类

##### 4.2.1.1 string 类
* string  等价于 System.String类
* string 虽然是引用类型，但是拥有``值语义`` 
* string 只读
````
string a = "mingchao";
string b = "mingchao";
System.Console.WriteLine(a==b); // True

string c = a;
a = "ting";
System.Console.WriteLine(c); // "mingchao"
````
#### 4.2.2 接口
* 无字段
#### 4.2.3 数组
```
int[] array1 = new int[5];

int[,] array2 = new int [2, 3];

int[][] jaggedArray = new int[6][];
jaggedArray[0] = new int[4] {1, 2, 3, 4};

```
#### 4.2.4 [委托](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/CSharp/Misc/Delegate.md)

## 5. 操作符／表达式
### 5.1  ``??``  null 合并运算符
```
using System;
public class Test{
	public static void Main() {
		int? x = null;
		int y = x ?? -1;
		Console.WriteLine(y);
	}
}
```
## 6. 流程控制

### 6.1 分支

#### 6.1.1 if-else

#### 6.1.2 switch
* C# 不允许Fall Through

### 6.2 循环

#### 6.2.1 while / do while

#### 6.2.2 for / foreach in

#### 6.2.3 yield
* [IEnumerator/IEnumerable](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/CSharp/Misc/IEnumerator_And_IEnumerable.md)
* [yield](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/CSharp/Misc/Yield.md)

## 7. 函数／模块

### 7.1 命名空间
* 使用 ``.`` 运算符分隔(嵌套)
* 使用 using xxx 指令可以在后面代码中省略类的命名空间
* 运算符 :: 用于命名空间使用了别名的情况
* global 命名空间是“根”命名空间, global::System 引用 System
* C# 没有头文件，代码分不分多个文件完全是为了编辑的方便，反正编译器都是一次读进合并起来编译成二进制文件，然后类和函数的签名都在metadata里面

### 7.2 预处理指令
* 折叠代码
```cs
    #region
    #endregion
```
## 8. 库相关

## 9. 黑科技
1. 分部类 partial 可把一个类分开实现
```
* 所有分部都需要指定partial
* 各部分必须具有相同的可访问性
* 基类，抽象，密封只需在任意部分声明
```
3. object
```
Object的别名
```
4. 属性
```
* get/set 访问器
* 最简单的作用：允许更改前验证数据
```
5. base
```
*  public MeClass(string from) : base(from)  在子类构造函数中，可以明确调用父类有参构造函数
```
6. virtual
```
* 子类可以不实现之，但如果实现就一定需要override关键字
```
7. 泛型
```
* 泛型类：相比使用object它类型安全，且没有装箱和拆箱的消耗
```
8. [ref out](Misc/Out.md)

9. params 未定个数参数

10. sealed
* override方法前使用：禁止派生类重写
* 类声明中使用：禁止派生
