# GCC 编译多个文件

## 多个文件
a.h
```C
int return1();
```

a.c
```C
int return1()
{
  return 1;
}
```

b.h
```C
int return2();
```

b.c
```C
int return2()
{
  return 2;
}
```

c.h
```C
int return3();
```

c.c
```C
int return3()
{
  return 3;
}
```

main.c
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

## 方法二 动态共享库
```shell
$ gcc -shared -fPIC a.c -o a.so
$ gcc -shared -fPIC b.c -o b.so
$ gcc -shared -fPIC c.c -o c.so
$ gcc main.c -L . a.so b.so c.so -o out
$ ./out
a:1
b:2
c:3
```

## 方法三 静态库
```shell
$ gcc -c a.c
$ gcc -c b.c
$ gcc -c c.c
$ ar -rc liballfiles.a a.o b.o c.o
$ gcc main.c -L . liballfiles -o out
$ ./out
a:1
b:2
c:3
```
