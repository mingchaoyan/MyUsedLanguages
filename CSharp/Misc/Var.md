# var

## 定义

从C# 3.0开始，方法中可以使用隐式变量，由编译器确定变量类型

## 例子

LINQ中
```cs
var custQuery = from cust in customers
                where cust.City == "Phoenix"
                select new { cust.Name, cust.Phone };

// var must be used because each item 
// in the sequence is an anonymous type
foreach (var item in custQuery)
{
    Console.WriteLine("Name={0}, Phone={1}", item.Name, item.Phone);
}
```
