```C 
int return1()
{
  return 1;
}
```

```C
int return2()
{
  return 2;
}
```

```C
int return3()
{
  return 3;
}
```

```C
#include "a.h"
#include "b.h"
#include "c.h"
#include "stdio.h"
int main()
{
  printf("a:%d\n", return1());
  printf("b:%d\n", return2());
  printf("c:%d\n", return3());
}
```
## 方法一 直接编译
```shell
$ gcc a.c b.c c.c main.c -o out
$ ./out
a:1
b:2
c:3
```
