# Indexer

## 简介
索引器允许类或者结构的实例像数组一样进行索引。
索引器类似于属性，不同之处在于他们取值函数采用参数。

## 例子
```
using System;
class SampleCollection<T>
{
	// Declare an array to store the data elements.
	private T[] arr = new T[100];

	// Define the indexer, which will allow client code
	// to use [] notation on the class instance itself.
	// (See line 2 of code in Main below.)        
	public T this[int i]
	{
		get
		{
			// This indexer is very simple, and just returns or sets
			// the corresponding element from the internal array.
			return arr[i];
		}
		set
		{
			arr[i] = value;
		}
	}
}

// This class shows how client code uses the indexer.
class Program
{
	static void Main(string[] args)
	{
		// Declare an instance of the SampleCollection type.
		SampleCollection<string> stringCollection = new SampleCollection<string>();

		// Use [] notation on the type.
		stringCollection[0] = "Hello, World";
		System.Console.WriteLine(stringCollection[0]);
	}
}
// Output:
// Hello, World.
```


