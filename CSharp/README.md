# C♯

## hello, world
```cs
public class Hello
{
  public static void Main()
  {
    System.Console.WriteLine("hello, world");
  }
}
```

## 历史
* 发行:2000
* 作者:安德斯·海尔斯伯格
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/CSharp/Anders_Hejlsberg.jpg)
* 设计初衷 微软为了对抗Java

## 黑科技
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
