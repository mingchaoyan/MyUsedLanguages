# C♯

## 0. hello, world
```cs
public class Hello
{
  public static void Main()
  {
    System.Console.WriteLine("hello, world");
  }
}
```

## 1. 历史
* 发行:2000
* 作者:安德斯·海尔斯伯格
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/CSharp/Anders_Hejlsberg.jpg)
* 设计初衷 微软为了对抗Java

## 2. 编程范型

## 3. 语言特性

## 4. 数据类型

## 5. 操作符／表达式

## 6. 流程控制

### 6.1 分支

#### 6.1.1 if-else

#### 6.1.2 else-if

#### 6.1.3 switch

### 6.2 循环

## 7. 函数／模块

### 7.1 命名空间
* 使用 . 运算符分隔
* 使用 using xxx 可以在后面代码中省略类的命名空间
* 运算符 :: 用于命名空间使用了别名的情况
* global 命名空间是“根”命名空间, global::System 引用 System
* C# 没有头文件，代码分不分多个文件完全是为了编辑的方便，反正编译器都是一次读进合并起来编译成二进制文件，然后类和函数的签名都在metadata里面

## 8. 库相关

## 9. 黑科技
1. 分部类 partial 可把一个类分开实现
```
* 所有分部都需要指定partial
* 各部分必须具有相同的可访问性
* 基类，抽象，密封只需在任意部分声明
```
2. 委托
```
* 委托是一个类，定义了方法的类型，使方法可以当作另一个方法的参数来传递
* 可以将多个方法绑定到同一个委托变量，当调用此变量的时候，依次调用所有绑定的方法
* event关键字，声明来一个封装的委托类型变量
* Action关键字，封装一个方法，改方法只有一个参数并不返回
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
7. 范型类
```
* 相比使用object它类型安全，且没有装箱和拆箱的消耗
```
