# Yield

## 定义
迭代器方法每次运行到yield return语句时，会返回一个表达式，并且保留当前在代码中的位置，当下次调用迭代器函数时从该位置重新启动。

## 例子
```CS
using System.Collections.Generic;
using System;
public class PowerOf2
{
	static void Main()
	{
		foreach (int i in Power(2, 8))
		{
			Console.Write("{0} ", i);
		}
	}

	public static IEnumerable<int> Power(int number, int exponent)
	{
		int result = 1;
		for(int i = 0; i< exponent; i++)
		{
			result = result * number;
			yield return result;
		}
	}
}
```
