# 委托

## 委托

### 定义
面向对象的，类型安全的和可靠的"函数指针"

### 格式
delegate 返回类型 委托名(参数列表)

### 例子

``` cs
public class TestDel
{
  // 声明一个委托
	public delegate void Del(string msg);

	public static void DelegeteMethod(string msg)
	{
		System.Console.WriteLine(msg);
	}
	public static void Main() 
	{

    // 实例化一个委托
		Del handler = DelegeteMethod;
		handler("hello, world");
	}
}
```

``` cs
using System;

namespace TestDelegate
{
	public delegate void GreetingDelegate(string name);
    class MainClass
    {
		private static void EnglishGreeting(string name) {
			Console.WriteLine("Morning, " + name);
		}

		private static void ChineseGreeting(string name) {
			Console.WriteLine("早上好，" + name);
		}

		private static void GreetPeople(string name, GreetingDelegate MakeGreeting) {
			MakeGreeting(name);
		}

        public static void Main(string[] args)
        {
			GreetPeople("mingchaoyan", EnglishGreeting);
			GreetPeople("严明超", ChineseGreeting);
        }
    }
}
```

## 事件

### 委托的多播
通过 += 运算符，可以添加方法到委托变量的调用列表。当委托调用时，这些方法都被调用

### 事件(event)定义
特殊类型的多播，仅可以从声明它们的类或结构中调用

### 格式
event 委托 委托变量

## Action 委托

### 定义
不具参数，不具返回值的委托。可省略此类委托声明。

### 例子
```cs
using System;

public class Name {
  private string _instanceName;
  public Name(string name) {
    this._instanceName = name;
  }

  public void Display() {
    Console.WriteLine(this._instanceName);
  }

//  public delegate void ShowValue();

  public class Test {
    public static void Main() {
      Name testName = new Name("mingchaoyan");
//      ShowValue showMethod = testName.Display;
      Action showMethod = testName.Display;
      showMethod();
    }
  }
}
```
