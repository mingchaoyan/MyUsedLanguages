# CoffeeScript

## hello,world
```coffeescript

```
## 历史
* 发行 2009
* 作者 Jeremy Ashkenas
* ![](https://github.com/mingchaoyan/MyUsedLanguages/blob/master/pic/CoffeeScript-Jeremy-Ashkenas-2009.jpg)

## 编程范型

* 面向对象（基于原型）
* 函数式
* 指令式
* 脚本语言

## 语言特性

## 数据类型
##### 基本类型（primitive types, typeof结果）

1. 布尔
2. undefined
3. 数字
4. 字符串
5. 对象(包括null)
6. 函数

##### 复合类型
7. 数组

## 操作符/关键字

* is
* isnt
* not
* and
* or
* true, yes, on
* false, no, off
* @, this
* of
* in
* a\*\*b (乘方)
* a//b （整除）
* a %% b （模）
* => fat arrow 绑定函数的this到当前值
* ? 存在性操作符，除非null或者undefined,否则都返回true
* 模式匹配
* \#{...} 字符串替换
* do 用来直接调用跟在后边的函数, 并且传递需要的参数.

## 流程控制
###分支

* if/else/then

```coffeescript
mood = greatlyImproved if singing

if happy and knowsIt
  clapsHands()
  chaChaCha()
else
  showIt()不同

date = if friday then sue else jill

if age < 21
    console.log "Young"
else if age < 65
    console.log "Adult"
else
    console.log “Senior"
```

* switch/when/else

```coffeescript
switch day
  when "Mon" then go work
  when "Tue" then go relax
  when "Thu" then go iceFishing
  when "Fri", "Sat"
    if day is bingoDay
      go bingo
      go dancing
  when "Sun" then go church
  else go work
```
### 循环

* 数组

```coffeescript
myArray = [1, 2, 3, 4, 5]
for number in myArray
    number + 1
# Output: 2, 3, 4, 5, 6
```

* 对象

```coffeescript
myObject =
    name: "Koen"
    city: "Amsterdam"
    age: 31

for key, value of myObject
    key, "=", value

# Output: name=Koen, city=Amsterdam, age=31
```
* 通用

```coffeescript
# 摇篮曲
num = 6
lyrics = while num -= 1
  "#{num} little monkeys, jumping on the bed.
    One fell out and bumped his head."
```
1. until关键字等同于while not, loop关键字 等同于while true

### 异常

```coffeescript
try
  allHellBreaksLoose()
  catsAndDogsLivingTogether()
catch error
  print error
finally
  cleanUp()
```

## 函数

### 示例
```coffeescript
square = (x) -> x * x
cube   = (x) -> square(x) * x
```
1. 支持默认参数

## 模块化

### 导出

```coffeescript
module.exports = xxx
```

### 导入
```coffeescript
require(some_module)
```

### 加载顺序
1. some_module 是核心模块，直接加载, 结束
2. some_module 以 . ./ ../ 开头按路径加载, 结束
3. 按路径加载 current_dir/node_modules/some_module
3.1. 加载成功结束；
3.2. 加载失败，令current_dir为父目录；
3.3. 重复这一过程，知道遇到根目录，抛出异常，结束。

## 特殊语法现象
