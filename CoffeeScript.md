# CoffeeScript

## 流程控制
###分支

* if/else/then

```coffeescript
mood = greatlyImproved if singing

if happy and knowsIt
  clapsHands()
  chaChaCha()
else
  showIt()

date = if friday then sue else jill
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

## 模块化

### 示例

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
       
