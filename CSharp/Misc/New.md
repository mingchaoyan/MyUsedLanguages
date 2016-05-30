# New

## 作为修饰符

### 简介
在用作声明修饰符时，new 关键字可以显式隐藏从基类继承的成员。如果不使用new将会收到警告。
注意：override是扩展基类的抽象。

### 例子
```
public class BaseC
{
    public static int x = 55;
    public static int y = 22;
}

public class DerivedC : BaseC
{
    // Hide field 'x'.
    new public static int x = 100;

    static void Main()
    {
        // Display the new value of x:
        Console.WriteLine(x);

        // Display the hidden value of x:
        Console.WriteLine(BaseC.x);

        // Display the unhidden member y:
        Console.WriteLine(y);
    }
}
/*
Output:
100
55
22
*/
```
