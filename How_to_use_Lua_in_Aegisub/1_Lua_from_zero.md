# 第一章 从零开始的Lua
> 本章主要简单介绍Lua是什么，Lua的基本数据类型，Lua的基本语法
>
> 按`Enter`键在右下角显示或隐藏目录
>
> 本章共 字 预计用时30min

---

<!-- toc -->

## 1.1 Lua是什么
Lua是一门基于C语言的扩展式程序设计语言，其开发目的是为了嵌入其他程序，为其提供丰富的功能。

作为一门扩展式语言，Lua 没有 "main" 程序的概念：它只能**嵌入**一个宿主程序中工作， 该宿主程序被称为**被嵌入程序**或者简称**宿主**。宿主程序可以调用函数执行一小段Lua 代码，可以读写 Lua 变量，可以注册 C 函数让 Lua 代码调用。 依靠 C 函数，Lua 可以共享相同的语法框架来定制编程语言，从而适用不同的领域。 

Lua是一门动态强类型非预定义语言。

什么？你不懂？emmmmm，来听我娓娓道来

动态类型(dynamic)，即类型随值不随变量。

强类型(strong)，即变量的值不可被隐式转换。

非预定义(implicit)，即变量可以不用声明类型。

![emmmmmmmm](image/20190413225143337_13621.jpg)

这样吧，举个例子

- 强类型(strong)就是你在种萝卜的时候，不能同时种两种萝卜，一个坑只能同时种一个
- 动态类型(dynamic)就是你可以中途把萝卜拔出来，重新种另一种进去
- 非预定义(implicit)就是你种萝卜可以不用挖坑，直接插进去就好

当然，上面的只是一个比较通俗的解释，**不一定正确严谨**，只是方便你的理解。如果你想要深入研究，请前往这个[wiki页面](https://www.wikiwand.com/en/Type_system#Explicit_or_implicit_declaration_and_inference)

---
## 1.2 Lua的基本数据类型
数据类型，即Data Type，就是八种属性的魔法
Lua中有八个基本类型

|类型|描述|
|:------:|:------|
|nil|只有`nil`属于该类型，即无效值，在逻辑判断中相当于`false`|
|boolean|布尔值，有`true`和`false`两种，用于逻辑判断|
|number|双精度类型的实浮点数如`3.14` `3`|
|string|字符串|
|table|关联数组|
|function|函数|
|userdata|C数据结构|
|thread|协程，用于并行执行|

你只需要学习其中的五个：`boolean number string table function`，其他的作为了解就好。

---
### 1.2.1 nil*了解即可*
`nil`是一个很特殊的类型，它是一个无效值，在逻辑判断中相当于`false`
现在打开你的Lua
像这样，把它拖进你的控制台
![](./image/20190414014737030_5274.png)
然后回车
![](./image/20190414014806814_27598.png)

然后输入下面的代码，以后都会这样给出一个例子让你自己去尝试

```Lua
--像这样的是注释，不用输入
print(Fubiki); -->nil
Fubiki = 'cat';
print(Fubiki);  -->"cat"
Fubiki = nil;
print(Fubiki); -->nil
```

nil的作用就是删除一个变量，以及判断该变量是否存在

```Lua
print(a);
if (a==nil) then
    print('a=nil');
else
    print('a!=nil');
end
--> nil
if (nil) then
    print('nil is true');
else
    print('nil is false');
end
--> nil is false
if (false==nil) then
    print('nil=false');
else
    print('nil is not false');
end
-->自己去试试看看出来什么结果吧
if (a) then
    print('a is here');
else
    print('a is not here');
end
-->自己去试试
```

在上面这个例子中可以看到，`nil`在逻辑判断中相当于`false`，即“假”，但是不等于`false`，只是相当于，所以`nil`这个类型可以被用来判断一个变量是否存在值，当然，如果`a=false`的话，和没有定义`a`是一样的，所以建议使用`type(a)=='nil'`来判断。

---
### 1.2.2 boolean

`boolean`又称为`布尔值`有`true(0)`和`false(1)`两种，经常用于逻辑判断。
常在`if`中用来作条件判断。值得一提的是，Lua与大部分语言相反，0为true，1为false

各位可以尝试一下下面这些例子
```Lua
Fubiki='cat';
print(Fubiki == 'cat');
if (Fubiki == "cat") then
    print('Nya Nya Nya');
else
    print('大楚兴，陈胜王');
end
```

### 1.2.3 number

在Lua中，`number`默认为双精度(double)，也就是说，以下这些值都是number型
```Lua
3.14
2
1e-2
4.7254e4
-23
0x3d
0xACBDAD
0x3e1
0/0
3*2
```

各位不妨用`print(type(...))`来看看
`Not a Number`(-nan(ind))是一个特殊的`number`，当你用`0/0`的时候会出现这个数值。

---
### 1.2.4 string
在Lua中，`String`(字符串)有三种定义方式，双引号`"String"`单引号`'String'`和中括号`[[String]]`

其中单引号和双引号定义的字符串**没有区别**，但是推荐用单引号，因为不用按shift

需要说一下的是第三种，用两个中括号括起来的字符串无视任何符号直到结束，也就是说你换行也还是一个字符串

```Lua
a = [[
    一行
    另一行
    第三行
    [=[
        第四行
        [==[
            内嵌的
            [===[
                理论上可以无限嵌套
            ]===]
            但是要正确闭合
        ]==]
    ]=]
]]
print(a)
```

在上面的例子中出现了多级的嵌套文本，为什么要这么定义，为什么要这么做？后面会讲到的

---
### 1.2.5 table
`table`是一个关联数组，在这里要说一下数组的概念

数组，就像这样: `{1,2,3,3,'',4,5,'apple',6,7,8,9,'a',f(x),{a,b}}`你可以往里面塞任何东西，就像你把东西编号一样，里面的两个逗号之间的东西，被称为元素(element)，又被称为值(value)，由于Lua的`table`是一个关联数组，所以在下文用`value`这一个说法

关联数组就是每个值都有与其对应的键(key)，可以理解为每个人都有他自己的身份证号和名字一样。在数组中，键是唯一的，就像你身份证号码是唯一的，但是你名字可以改。

键值对，即键与值的组合，叫做键值对。
```Lua
groups = {Sakyu = 'https://space.bilibili.com/1612112'};
print(groups);
groups['A.I.Channel'] = 'https://space.bilibili.com/1473830';
groups.Aqua = 'https://space.bilibili.com/375504219';
print(groups);
print(groups.Aqua);
print(groups.Sakyu);
print(groups['A.I.Channel']);

appear_time = {'A.I.Channel','Akari','Luna'} ;
--这里是出现时间顺序，我不知道有没有记错XD
print(appear_time[0]);
print(appear_time[1]);
appear_time[3]='Siro';
print(appear_time[3]);

fans={Tamaki:114510};
print(fans.Tamaki);
fans.Tamaki=114514;
print(fans.Tamaki);
```

Lua中的键值对使用`key = value`的形式，key为`数字(number)`或`字符串(string)`的其中一种，value可以是任何东西。你可以用`table.key`这种简单的方式来获取table中与key相对应的值，也可以对其修改,或创建不存在的键值对，统称访问。

但是出现以下两种情况的时候必须使用`table[key]`这种形式去访问键值。

1. 键的开头为数字，如`1` `11区`等等
2. 键中有`.`，如`A.I.Channel` `youtu.be`

特别指出：一个可以完全表示为整数的浮点数和对应的整数相等 例如：`1.0 == 1`。 为了消除歧义，当一个可以完全表示为整数的浮点数做为键值时， 都会被转换为对应的整数储存。例如，当你写 `a[2.0] = true` 时，实际被插入表中的键是整数`2`。 

（另一方面，`2`与`"2"`是两个不同的值，故而它们可以是同一张表中的不同项。） 

关于table的更多用法后续章节会提到

---
### 1.2.6 funtion
`function`(函数)是一个语句的集合，可以理解为一个由多个小魔法组成的大魔法。

Lua可以调用（以及操作）用Lua或C编写的函数。

其参数由编写的时候定义，Lua支持可变参数。

```Lua
function plus(a,b)
    if (type(a)==type(b)) then
        if (type(a)=='number') then
            c = a + b;
        elseif (type(a)=='string') then
            c = a..b;
        end
    else
        c = string.format('%s%s',a,b);
    end
    return c    
end

print(plus(4,3)); --> 7
print(plus(4,'1')); --> 41
print(plus('l','a')); --> la
print(type(plus)); -->function
```

上面这个函数展示了一个简单的功能，将提供的两个参数进行判断，如果是两个数字，就加起来，如果是字符串，就连接起来。因为Lua是强类型语言，所以如果不做显式转换，它不能进行直接的连接。

关于函数，这里只作一个简单的介绍，后面会更加详细的展开

---
### 1.2.7 userdata*了解即可*
`userdata` 类型允许将`C`中的数据保存在`Lua变量`中。

用户数据类型的值是一个`内存块`，有两种用户数据：

- 完全用户数据，指一块由Lua管理的内存对应的对象；
- 轻量用户数据，指一个简单的`C 指针`。 

用户数据在Lua中除了赋值与相等性判断之外没有其他预定义的操作。

通过使用`元表`，程序员可以给完全用户数据定义一系列的操作。

你**只能**通过`C API`而无法在`Lua代码`中创建或者修改用户数据的值，这保证了数据仅被宿主程序所控制。 

想要了解更多，请前往[此处](http://www.runoob.com/manual/lua53doc/manual.html#6.2)

---
### 1.2.8 thread*了解即可*
`thread`类型表示了一个独立的执行序列，被用于实现协程。

`Lua`的线程与操作系统的线程毫无关系。

`Lua`为所有的系统，包括那些不支持原生线程的系统，提供了协程支持。

`协程`，即协同进程，即多个进程并行执行

想了解更多，可以看[这里](http://www.runoob.com/manual/lua53doc/manual.html#2.6)

---
## 1.3 Lua的基本语法
> 本章主要介绍在Lua中基本的一些语法规则
> 很简单的，相信我

---
### 1.3.1 标识命名规定
标识符，即用于标识不同的变量与函数的字符组合

在Lua中，你可以使用`a-z A-Z`以及下划线(`_`)开头加数字来作为标识符

**不允许**使用纯数字以及数字开头的标识符

**不建议**使用下划线加大写字母(如`_A`)来作为标识符

Lua是**大小写敏感**的，也就是说`Apple`和`apple`是不同的两个标识符

以下这些为系统保留的，**不允许**作为标识符
```
and       break     do        else      elseif    end
false     for       function  goto      if        in
local     nil       not       or        repeat    return
then      true      until     while
```

以下这些**字符**不能出现在标识符中，因为是运算符
```
+     -     *     /     %     ^     #
&     ~     |     <<    >>    //
==    ~=    <=    >=    <     >     =
(     )     {     }     [     ]     ::
;     :     ,     .     ..    ...
```

以下这些为允许的标识符的例子
```
And
fubiki 
SihaSiha 
_HomoLive 
_114514 
timetable1
```

以下这些为**不允许**的标识符的例子
```Text
1551
114514inm
```
- **建议**使用`小驼峰命名法`作为函数标识符，如`getPicture` `countAppleNumber`
- **建议**使用`小写字母下划线命名法`作为一般变量标识符，如`picture_url` `picture_url_number`
- **建议**使用`大写字母下划线命名法`作为全局变量标识符，如`PICTURE_WIDTH` `FILE_PATH`
- **不建议**使用`the` `of`等连词，如`the_apple` `width_of_picture`

---
### 1.3.2 注释
Lua中严格来说只有单行注释，以两个“减号”`--`开头的行为注释

你可以以`[[ ]]`包裹多行代码，并在其前面加上`--`令其成为多行注释

前面说过，用`[[ ]]`包裹的字符，忽略一切换行，作为一行，所以在开头加上`--`可以启用多行注释

**建议**使用`--[[ --]]`来包裹多行注释，这种注释可以只做一处修改来取消注释

```Lua
--[[
function plus(a,b)
    if (type(a)==type(b)) then
        if (type(a)=='number') then
            c = a + b;
        elseif (type(a)=='string') then
            c = a..b;
        end
    else
        c = string.format('%s%s',a,b);
    end
    return c; 
end
--]]
```

需要取消注释，只需要在最前面加上一个`-`
```Lua
---[[
function plus(a,b)
    if (type(a)==type(b)) then
        if (type(a)=='number') then
            c = a + b;
        elseif (type(a)=='string') then
            c = a..b;
        end
    else
        c = string.format('%s%s',a,b);
    end
    return c;
end
--]]
```

发生了什么呢？

很简单

`[[...........]]`之间无论多少换行，都是一行，前面的`--`把这一行注释掉了

那么我在前面加上一个`-`那么就会把`-[[`注释掉令其重新变成多行，而最后添加的`--]]`是一个注释行，把多行注释变成了两个单行注释和在其之间的多行代码

---
### 1.3.3 变量
Lua有词法作用范围。变量的作用范围**开始**于声明它们之后的第一个语句段，**结束**于包含这个声明的最内层语句块的最后一个非空语句。声明于最外层的变量为全局变量。

很难理解吗

嘛，举个例子吧。就像通用货币和地方货币一样，通用货币全球都能用，地方货币只能在一个地方用，在其他地方就要通过一些手续来转换转出。

你可以通过以下方法来声明变量
```Lua
a = 0;
local b;
c = 4;
function d(num)
    a = num*2;
    return a
end

print(d(2)); -->4
d(2);
print(a); -->0
```

==这个例子中用了极其随便的命名方法，不要效仿==

你可以看到，在函数内部声明的变量在外面是无法访问的。只能通过`return`来返回值。

**建议**在函数内部声明局部变量时使用`local`，这是为了防止命名重复与变量污染。

---
### 1.3.4 语句

`Lua`支持所有与`Pascal`或是`C`类似的常见形式的语句，这个集合包括赋值，控制结构，函数调用，还有变量声明。

啥？你说你又看不懂了？

`赋值`，就是类似`Fubiki = 'neko'`这样的句子，这样的句子我们成为赋值句

`条件表达式`，就是`if` `while` `for`等这样的句子

`函数调用`，就是`函数名(参数)`这样的一个结构的句子

`变量声明`，就是只声明而不赋值，如`local a`，生动来说，就是~~占着茅坑不拉屎~~挖个坑不种萝卜

#### 1.3.4.1 语句块

语句块就是一个语句序列，他们会按次序执行

`Lua`以换行或分号`;`来分隔语句，或以分号`;`来开始一个语句块

来看看官方文档的一个小例子

```Lua
a = b + c
(print or io.write)('done')
```

从语法上来讲，这有两种解释方式

```lua
a = b + c(print or io.write)('done')
a = b + c; (print or io.write)('done')
```

而当前版本的Lua编译器总是以第一种结构来解析，他会将其理解为一个函数调用

所以建议在语句后面加上`;`来结束语句，这是一个好习惯，以免出现想不到的错误

语句块通常指的是多条语句

```lua
function a(a)
    print(a);
    print(string.format("%s%s%s",a,a,a));
end
```



而一个语句块可以被显式地定界为单条语句

```lua
do local a = 1 end
```

这种方法一般被用来控制变量声明的作用域，有时显式定界也用于在一个语句块中插入`return`

#### 1.3.4.2 赋值

Lua允许多重赋值，你问啥是多重赋值？上例子

```Lua
a, b, c, d = 1, 2, 3, 4;
-- a=1 b=2 c=3 d=4
d, e, f = 1;
-- d=1 e=nil f=nil
h = {}
g = 2
g ,h[g] = g+1, 123
```

Lua总是在表达式完成运算后，再做赋值操作

所以上面例子中的最后一句，`h[2]=123`而不会影响到`h[3]`

所以你可以使用`x,y=y,x`这样的语句来交换x和y的值

#### 1.3.4.3 条件表达式

条件表达式是指`if` `while` `repeat`以及`for`，在lua中，`for`有两种形式。

```lua
if exp then
    --some code
elseif exp then
    --some code
else
    --some code
end
```





### 1.3.5 表达式

#### 1.3.5.1 数学运算

#### 1.3.5.2 比较 逻辑

#### 1.3.5.3 字符串操作

#### 1.3.5.4 优先级

#### 1.3.5.5 函数

## 1.4 Lua的标准函数库

### 1.4.1 基础函数

### 1.4.2 模块

### 1.4.3 数学函数

### 1.4.4 Aegisub的拓展



---
最后修改

Gerardyang

20190423

本文无法遵守996 License

修改历史

190423 升级CC-BY-SA协议

190414 最初动笔

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/">知识共享署名-相同方式共享 4.0 国际许可协议</a>进行许可。