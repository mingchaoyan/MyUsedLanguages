# Ruby

## hello, world
* REPL
```ruby
$ irb
irb(main):001:0> puts "hello, world"
hello, world
=> nil
irb(main):002:0> exit
```

* File
helle.rb
```ruby
#!/usr/bin/env ruby
puts "Hello, world!"
```
```shell
ruby hello.rb
```
## 历史
* 发行 1995
* 作者 Yukihiro Matsumoto(日本)
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/Ruby/Yukihiro_Matsumoto.JPG)
* 设计初衷 减少编程时候的不必要的琐碎时间，令编写程序的人高兴

## 编程范型
* 面向对象
* 指令式
* 函数式
* 反射

## 数据类型
* 动态弱类型
* 只有对象，没有基础类型

### 数组
* 下标从0开始
* 可以使用-1，表示倒数第1个

### 散列表
* key-value

## 面向对象
```ruby
class Mammal
  def breathe
    puts "inhale and exhale"
  end
end

class Cat < Mammal
  def speak
    puts "Meow"
  end
end

paris = Cat.new
paris.breathe
paris.speak
```
## 流程控制
### 分支
* 除了nil和false，其他值都代表true
* 逻辑运算符(短路版本 && and || or; 非短路版本 & |)

#### 单行形式
```ruby
puts "hello, world" if x == 42
puts "hello, world" unless x == 42
```

#### 块形式
```ruby
kind =
  case year
  when 1850..1889 then 'Blues'
  when 1890..1909 then 'Ragtime'
  when 1910..1929 then 'New Orleans Jazz'
  when 1930..1939 then 'Swing'
  when 1940..1950 then 'Bebop'
  else 'Jazz'
  end
```
```ruby
result =
  if some_cond
    calc_something
  else
    calc_something_else
  end
```
### 循环
#### 单行形式
```ruby
x = x + 1 while x < 10

x = x - 1 untils x == 1
```
#### 块形式
```ruby
while x < 10
  x = x + 1
  puts x
end
```

## 函数
### 示例
1. 支持默认参数

## 模块
### 包管理器
Gem
