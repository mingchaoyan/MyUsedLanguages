# IEnumerator and IEnumerable

## IEnumerator

* 枚举中的个体，如Person
* 需要实现MoveNext(), Reset() 两个方法，Current一个属性

## IEnumerable

* 一个可枚举的集合，如People
* 需要实现GetEnumerator()一个方法

## 例子
```cs
using System;
using System.Collections;

public class Person
{
	public Person(string fName, string lName)
	{
		this.firstName = fName;
		this.lastName = lName;
	}

	public string firstName;
	public string lastName;
}

public class People:IEnumerable
{
	private Person[] _people;
	public People(Person[] pArray)
	{
		_people = new Person[pArray.Length];
		for(int i = 0; i < pArray.Length; i++)
		{
			_people[i] = pArray[i];
		}
	}
	IEnumerator IEnumerable.GetEnumerator()
	{
		return (IEnumerator) GetEnumerator();
	}
	public PeopleEnum GetEnumerator()
	{
		return new PeopleEnum(_people);
	}
}

public class PeopleEnum : IEnumerator
{
	public Person[] _people;
	int position = -1;
	public PeopleEnum(Person[] list) {
		_people = list;
	}

	public bool MoveNext()
	{
		position++;
		return (position < _people.Length);
	}
	public void Reset()
	{
		position = -1;
	}

	object IEnumerator.Current
	{
		get
		{
			return Current;
		}
	}

	public Person Current
	{
		get
		{
			try 
			{
				return _people[position];
			}
			catch (IndexOutOfRangeException)
			{
				throw new InvalidOperationException();
			}
		}
	}
}

class TestEnum
{
	static void Main()
	{
		Person[] peopleArray = new Person[3]
		{
			new Person("mingchao", "yan"),
			new Person("weiting", "mao"),
			new Person("test", "test")
		};
		People peopleList = new People(peopleArray);
		foreach(Person p in peopleList)
			Console.WriteLine(p.firstName + " " + p.lastName);
	}
}
```
