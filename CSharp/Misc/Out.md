# out 参数修饰符

## 定义

通过引用传递参数, 在需要返回多个值时比较有用。

## 例子

```cs
class OutReturnExample {
	static void Method(out int i, out string s, out string s2)
	{
		i = 44;
		s = "I've been returned";
		s2 = null;
	}

	static void Main() {
		int value;
		string s1, s2;
		Method(out value, out s1, out s2);
		System.Console.Write("value: {0},\n s1:{1},\n s2:{2}\n", value, s1, s2);
	}
}
```
