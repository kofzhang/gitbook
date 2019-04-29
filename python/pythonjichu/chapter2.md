# 第二章 Python入门

## 什么是计算机语言

计算机就是一台用来计算的机器，人让计算机干什么计算机就得干什么！

需要通过计算机的语言来控制计算机（编程语言）

计算机语言其实和人类的语言没有本质的区别，不同点就是交流的主体不同！

计算机语言发展经历了三个阶段：

> **机器语言**
>
> ​	机器语言通过二进制编码来编写程序
>
> ​	执行效率高，编写起来太麻烦
>
> **汇编语言**
>
> ​	使用符号来代替机器码
>
> ​	编写程序时，不需要使用二进制，而是直接编写符号
>
> ​	编写完成后，需要将符号转换为机器码，然后再由计算机执行
>
> ​		将符号转换为机器码的过程称为汇编
>
> ​		将机器码族汉换为符号的过程，称为反汇编
>
> ​	汇编语言一般只适用于某些硬件，兼容性比较差
>
> **高级语言**
>
> ​	高级语言的语法基本和现在英语语法类似，并且和硬件的关系没有那么紧密了
>
> ​	也就是说我们通过高级语言开发程序可以在不同的硬件系统中执行
>
> ​	并且高级语言学习起来也更加的容易，现在我们知道的语言基本都是高级语言
>
> ​	C、C++、C#、Java、Javascript、Python ......

## 编译型语言和解释型语言

计算机只能识别二进制编码（机器码），所以任何的语言在交由计算机执行时必须要先转换为机器码，也就是像print(‘hello’)必须要转换为类似 1010101 这样的机器码



根据转换时机的不同，语言分成了两大类：

编译型语言

> C语言
>
> 编译型语言，会在代码执行前将代码编译为机器码，然后将机器码交由计算机执行
>
> a（源码）——编译——> b（编译后的机器码）
>
> 特点：
>
> ​	执行速度特别快
>
> ​	跨平台性比较差

解释型语言

> Python JS Java
>
> 解释型语言，不会在执行前对代码进行编译，而是在执行的同时一遍执行一遍编译
>
> a（源码）——解释器——>解释执行
>
> 特点：
>
> ​	执行速度比较慢
>
> ​	跨平台性比较好



## Python的介绍

Python也是解释型语言

> Python is an interpreted, high-level, general-purpose programming language. Created by Guido van Rossum and first released in 1991, Python has a design philosophy that emphasizes code readability, notably using significant whitespace. It provides constructs that enable clear programming on both small and large scales.[26] Van Rossum led the language community until stepping down as leader in July 2018.
>
> <font color=red>Python是一种广泛使用的高级编程语言，属于通用型编程语言，由吉多·范罗苏姆创造，第一版发行于1991年。可以视之为一种改良（加入一些其他编程语言的优点，如面向对象）的LISP。作为一种解释型语言，Python的设计哲学强调代码的可读性和简洁的语法（尤其是使用空格缩进划分代码块，而非使用大括号或者关键词）。相比于C++或Java，Python让开发者能够用更少的代码表达想法。不管是小型还是大型程序，改语言都试图让程序的结构清晰明了。</font>
>
> Python features a dynamic type system and automatic memory management. It supports multiple programming paradigms, including object-oriented, imperative, functional and procedural. It also has a comprehensive standard library.
>
> <font color=red>Python拥有动态类型系统和垃圾回收功能，能够自动管理内存使用，并且支持多种编程范式，包括面向对象、命令式、函数式和过程式编程。其本身拥有一个巨大而广泛的标准库。</font>
>
> Python interpreters are available for many operating systems. CPython, the reference implementation of Python, is open source software[30] and has a community-based development model, as do nearly all of Python's other implementations. Python and CPython are managed by the non-profit Python Software Foundation. 
>
> <font color=red>Python解释器本身几乎可以在所有操作系统中运行。Python的正式解释器CPython是用C语言编写的、是一个由社区驱动的自由软件，目前由Python软件基金会管理。</font>



Life is short you need Python(人生苦短，我用Python)



Python的用途：

​	WEB应用

​		Facebook 豆瓣 ……

​	爬虫程序

​	科学计算

​	自动化运维

​	大数据（数据清洗）

​	云计算

​	人工智能

​	桌面软件/游戏

​	……

**编程语言排名**

![1552888887901](D:/OneDrive%E5%85%B1%E4%BA%AB%E6%96%87%E4%BB%B6%E5%A4%B9/OneDrive%20-%20hebmu.edu.cn/%E4%B8%AA%E4%BA%BA%E5%AD%A6%E4%B9%A0/Python/Python%E8%AE%B2%E4%B9%89/%E7%AC%AC%E4%BA%8C%E7%AB%A0_Python%E5%85%A5%E9%97%A8.assets/1552888887901.png)

![1552888902321](D:/OneDrive%E5%85%B1%E4%BA%AB%E6%96%87%E4%BB%B6%E5%A4%B9/OneDrive%20-%20hebmu.edu.cn/%E4%B8%AA%E4%BA%BA%E5%AD%A6%E4%B9%A0/Python/Python%E8%AE%B2%E4%B9%89/%E7%AC%AC%E4%BA%8C%E7%AB%A0_Python%E5%85%A5%E9%97%A8.assets/1552888902321.png)



## Python开发环境搭建

开发环境搭建就是安装Python的解释器

Python的解释器分类：

​	CPython（官方）

​		用C语言编写的Python解释器

​	PyPy

​		用Python语言编写的Python解释器

​	IronPython

​		用.net编写的Python解释器

​	Jython

​		用Java编写的Python解释器

步骤：

​	1.下载安装包

​		3.x

​		2.x

​	2.安装（傻瓜式安装）

​	3.打开命令行窗口，输入python  出现如下内容

```python
Python 3.6.5 (v3.6.5:f59c0932b4, Mar 28 2018, 16:07:46) [MSC v.1900 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

## Python的交互界面

当我们通过命令行来输入Python，所进入到的界面就是Python的交互界面

结构：

​	版本和版权声明：

```python
Python 3.6.5 (v3.6.5:f59c0932b4, Mar 28 2018, 16:07:46) [MSC v.1900 32 bit (Intel)] on win32
Type "help", "copyright", "credits" or "license" for more information.
```

​	命令提示符：

```python
>>>
```

​	在命令提示符后可以直接输入Python的指令！输入完的指令将会被Python的解释器立即执行！

​	安装Python的同时，会自动安装一个Python的开发工具IDLE，通过IDLE也可以进入到交互模式，但是不同的是，在IDLE中可以通过TAB键来查看语句的提示。

​	IDEL实际上就是一个交互界面，但是他可以有一些简单的提示，并且可以将代码保存。

交互模式只能你输入一行代码，它就执行一行，所以他并不适用于我们日常的开发！仅可以用来做一些日常的简单的测试！

我们一般会将Python代码编写到一个py文件中，然后通过python指令来执行文件中的代码。



练习：

​	自己尝试创建一个py文件，并向文件中写入python打印语句（print…）然后执行该文件。

​	如果你的系统的扩展名无法修改，请尝试自行Baidu！

## 几个概念

1.表达式

​	表达式就是一个类似于数学公式的东西

​	比如： 10 + 5    8 - 4

​	表达式一般仅仅用了计算一些结果，不会对程序产生实质性的影响

​	如果在交互模式中输入一个表达式，解释器会自动将表达式的结果输出



2.语句

​	在程序中语句一般需要完成某种功能，比如打印信息、获取信息、为变量赋值……

​	比如：

```python
print()
a = 10
```

​	语句的执行一般会对程序产生一定的影响

​	在交互模式中不一定会输出语句的执行结果

3.程序（program）

​	程序就是由一条一条的语句和一条一条的表达式构成的。

4.函数（function）

​	函数就是一种语句，函数专门用来完成特定的功能

​	函数长得形如：xxx()

​	函数的分类：

​		内置函数

​			由Python解释器提供的函数，可以在Python中直接使用

​		自定义函数

​			由程序员自主创建的函数

​	当我们需要完成某个功能时，就可以去调用内置函数，或者自定义函数

​	函数的两个要素：

​		参数

​			（）中的内容就是函数的参数

​			函数中可以没有参数，也可以有多个参数，多个参数之间使用，（逗号）隔开

​		返回值

​			返回值是函数的返回结果，不是所有的函数都有返回值

## 基本语法

1.在Python中严格区分大小写

2.在Python中的每一行就是一条语句，每条语句以换行结束

3.Python中每一行语句不要过长（规范中建议每行不要超过80个字符）

4.一条语句可以分多行编写，多行编写时，语句后面以\（反斜杠）结尾

5.Python是缩进严格的语言，所以在Python中不要随便写缩进

6.在Python中使用#来表示注释，#后的内容都属于注释，注释的内容将会被解释器所忽略。

​	我们可以通过注释来对程序进行解释说明，一定要养成良好的编写注释的习惯

​	注释要求简单明了，一般习惯上#后面会跟着一个空格

## 字面量和变量

**字面量**就是一个一个的值，比如：1,2,3,4,5,6，’HELLO‘

​	字面量所表示的意思就是它的字面的值，在程序中可以直接使用字面量

**变量**（variable）变量可以用来保存字面量，并且保存中保存的字面量是不定的

​	变量本身没有任何意思，它会根据不同的字面量表示不同的意思

```python
a = 10
```

一般我们在开发时，很少直接使用字面量，都是将字面量保存到变量中，通过变量来引用字面量

```python
salary = 123456789
```

## 变量和标识符

```python
# Python中使用变量不需要声明，直接为变量赋值即可
a = 10

# 不能使用没有进行过赋值的变量
# 如果使用没有赋值过的变量，会报告 NameError： name ’b‘ is not defined
print(a)

# Python是一个动态类型的语言，可以为变量赋值任意类型的值，也可以任意修改变量的值

# 标识符
# 在Python中所有可以自主命名的内容都属于标识符
# 比如：变量名、函数名、类名
# 标识符必须遵循标识符的规范
# 	1.标识符中可以含有字幕、数字、下划线，但是不能使用数字开头
#		例子：a_1   _a1  _1a  
#   2.标识符不能是Python中的关键字和保留字
#		也不建议使用Python中的函数名作为标识符，因为这样会导致函数被覆盖
#	3.命名规范
#		在Python中注意遵循两种命名规范：
#			下划线命名法
#				所有字母小写，单词之间使用_分隔
#				max_length min_length hello_world xxx_yyy_zzz
#			帕斯卡命名法（大驼峰命名法）
#				首字母大写，每个单词开头字母大写，其余字母小写
#				MaxLength MinLength HelloWorld XxxYyyZzz
#   如果使用不符合标准的标识符，将会报错  SyntaxError: invalid syntax

```

练习1：尝试自己定义几个变量（复杂一些，尝试不同的命名法），然后打印一些变量

练习2：通过搜索引擎搜索还有哪些其他的命名规范

## 数据类型

数据类型指的就是变量的值得类型，也就是可以为变量赋哪些值

数值

​	整型

​	布尔值

​	浮点型

​	复数

字符串

空值	

```python
# 在Python中数值分成了三种：整数、浮点数（小数）、复数
# 在Python中所有的整数都是int类型
a = 10
b = 20
# Python中的整数的大小没有限制，可以是一个无限大的整数
# 如果数字的长度过大，可以使用下划线作为分隔符

c = 123_456_789

# 其他进制的数
# d = 0123 十进制数不能以0开头
# 其他进制的整数，只要是数字打印时一定是以十进制的形式显示的
# 二进制 0b开头
c = 0b10 # 二进制的10
# 八进制 0o开头
c = 0o10
# 十六进制 0x开头
c = 0x10

# 也可以通过运算符来对数字进行运算，并且可以保证整数运算的精确
c = 100
c = c + 3

# 浮点数（小数），在Python中所有的小数都是float类型
c = 1.23
c = 4.56

# 对浮点数进行运算时，可能会得到一个不精确的结果
c = 0.1 + 0.2  # 0.3000000000000004

print(c)
```

```python
# 字符串
# 字符串用来表示一段文本信息，字符串是程序中使用的最多的数据类型
# 在Python中字符串需要使用引号引起来

s = 'hello'

# s = abc # 字符串必须使用引号引起来，不使用不是字符串
# 引号可以是双引号也可以是单引号，但是注意不要混用
s = 'hello'
s = "hello"
# s = 'hello" 引号不能混合使用，SyntaxError：EOL while scanning string literal
# 相同的引号之间不能嵌套
# s = "子曰："学而时习之，乐呵乐呵！""
s = '子曰："学而时习之，乐呵乐呵！"'

# 长字符串
# 单引号和双引号不能跨行使用
s = ‘锄禾日当午，\
汗滴禾下土，\
谁知盘中餐，\
粒粒皆辛苦’

# 使用三重引号来表示一个长字符串 ''' """
# 三重引号可以换行，并且保留字符串中的格式

s = """锄禾日当午，
汗滴禾下土，
谁知盘中餐，
粒粒皆辛苦"""

# 转义字符
# 可以使用 \ 作为转义字符，通过转义字符，可以在字符串中使用一些特殊的内容
# 例子：
# 	\' 表示'
#	\" 表示"
# 	\t 表示制表符
# 	\n 表示换行符
# 	\\ 表示反斜杠
# 	\uxxxx 表示Unicode编码
s = "子曰：\"学而时习之，乐呵乐呵！\""

s = '\u0040'

print(s)

```

```python
# 格式化字符串

a = 'hello'
# 字符串之间也可以进行加法运算
# 如果将两个字符串进行相加，则会自动将两个字符串拼接为一个
a = 'abc' + 'haha' + '哈哈'
# a = 123
# 字符串不能喝其他类型进行加法运算，否则会出现异常 TypeError: must be str, not int
# print("a = " + a) # 这种写法在Python中不常见

a = 123
# print('a = ',a)

# 在创建字符串时，可以在字符串中指定占位符
# %s 在字符串中表示任意字符
# %f 浮点数占位符
# %d 整数占位符
b = 'Hello %s'%'孙悟空'
b = 'Hello %s 你好 %s'%('tom','孙悟空')
b = 'hello %3.5s'%'ab' # %3.5s自负粗汉的长度限制在3-5之间
b = 'hello %s'%123.5
b = 'hello %.2f'%123.456
b = 'hello %d'%123.95

# print('a = %s'%a)

# 格式化自负粗汉，可以通过在字符串前添加一个f来创建一个格式化字符串
# 在格式化字符串中可以直接嵌入变量
c = f'hello {a} {b}'

print(f'a = {a}')

```

练习：创建一个变量保存你的名字，然后通过四种格式化字符串的方式来输出“欢迎 xxx 光临！“

```python
# 创建一个变量来保存你的名字
name = '孙悟空'

# 使用四种方式来输出，欢迎 xxx 光临
# 拼串
print('欢迎 '+name+' 光临！')
# 多个参数
print('欢迎'，name，'光临！')
# 占位符
print('欢迎 %s 光临！'%name)
# 格式化字符串
print(f'欢迎 {name} 光临！')

# 字符串的复制（将字符串和数字相乘）
a = 'abc'
# * 在语言中标识乘法
# 如果将字符串和数字相乘，则解释器会将字符串重复指定的次数并返回
a = a * 2
print(a)

```

```python
# 布尔值（boolean bool）
# 布尔值主要用来做逻辑判断
# 布尔值一共有两个  True 和 False
# True标识真，False标识假
a = True
a = False
print('a = ',a)

# 布尔值实际上也属于整形，True就相当于1，False就相当于0
print(1 + True)

# None(空值)
# None专门用来表示不存在
b = None
print(b)

```

## 类型检查

```python
# 通过类型检查，可以检查变量的类型
a = 123
b = '123'

print('a = ',a)
print('b = ',b)

# type() 用来检查值得类型
# 该函数会将检查的结果作为返回值返回，可以通过变量来接收函数的返回值
c = type('123')
c = type(a)
print(c)
print(type(1)) # <class 'int'>
print(type(1.5)) # <class 'float'>
print(type(True)) # <class 'bool'>
print(type('hello')) # <class 'str'>
print(type(None)) # <class 'Nonetype'>

```

## 对象（object）

Python是一门面向对象的语言

一切皆对象！

程序运行当中，所有的数据都是存储到内存当中然后再运行的！

对象就是内存中专门用来存储指定数据的一块区域

对象实际上就是一个容器，专门用来存储数据

像我们之前学习的数值、字符串、布尔值、None都是对象

## 对象的结构

每个对象中都要保存三种数据

- id（标识）

  ​	id用来表示对象的唯一性，每一个对象都有唯一的id

  ​	对象的id就相当于人的身份证号一样

  ​	可以通过id()函数来查看对象的id

  ​	id是由解析器生成的，在CPython中，id就是对象的内存地址

  ​	对象一旦创建，则它的id永远不能再改变

- type（类型）

  ​	类型用来表示当前对象所属的类型

  ​	比如：int str float bool ……

  ​	类型决定了对象有哪些功能

  ​	通过type()函数来查看对象的类型

  ​	Python是一门强类型的语言，对象一旦创建类型便不能改变

- value（值）

  ​	值就是对象中存储的具体的数据

  ​	对于有些对象值是可以改变的

  ​	对象分成两大类，可变对象、不可变对象

  ​		可变对象的值可以改变

  ​		不可变对象的值不能改变，之前学习的对象都是不可变对象

练习：尝试自己画一下对象的内存结构。

## 变量和对象

对象并没有直接存储到变量中，在Python中变量更像是给对象齐了一个别名

变量中存储的不是对象的值，而是对象的id（内存地址），当我们使用变量时，实际上就是在通过对象id在查找对象

变量中保存的对象，只有在为变量重新赋值时才会改变

变量和变量之间是相互独立的，修改一个变量不会影响另一个变量



## 类型转换

所谓的类型转换，将一个类型的对象转换为其他对象

类型转换不是改变对象本身的类型，而是根据当前对象的值创建一个新的对象

```python
# 类型转换的四个函数 int() float() str() bool()
# int()可以用来将其他的对象转换为整型
# 规则：
#	布尔值：True -> 1	False -> 0
#	浮点数：直接取整，省略小数点后的内容
#	字符串：合法的整数字符串，直接转换为对应的数字
#		如果不是合法的整数字符串，则报错 ValueError：invalid literal for int() with bas
# 	对于其他不可转换为整型的对象，直接抛出异常 ValueError
#	float()和int()基本一致，不同的是它会将对象转换为浮点数
#	str()可以将对象转换为字符串
#	True -> 'True'
#	False -> 'False'
#	bool()可以将对象转换为布尔值，任何对象都可以转换为布尔值
#		规则：对于所有表示空性的对象都会转换为False，其余转换为True
#		哪些表示的空性：0、None、''...

a = True

# 调用int()来将a转换为整型
# int()函数不会对原来的变量产生影响，他是对象转换为指定类型，并将其作为返回值返回
# 如果希望修改原来的变量，则需要对变量进行重新赋值
a = int(a)

a = False
a = int(a)

a = '123'
a = int(a)

a = 11.6
a = int(a)

a = '11.5'
# a = int(a)

print('a = ',a)
print('a的类型是',type(a))

```

## 运算符（操作符）

运算符可以对一个值或多个值进行运算或各种操作

比如：+、-、=都属于运算符

运算符分类：

1. 算术运算符
2. 赋值运算符
3. 比较运算符（关系运算符）
4. 逻辑运算符
5. 条件运算符（三元运算符）

```python
# 算数运算符
#	+ 加法运算符（如果是两个字符串之间进行加法运算，则会进行拼串操作）
#	- 减法运算符
#	* 乘法运算符（如果将字符串和数字相乘，则会对字符串进行复制操作，将字符串重复指定次数
#	/ 除法运算符
#	// 整除运算符，只会保留计算后的整数位
# 	** 幂运算
#	% 模运算，求两个数相除的余数

a = 10 + 5 #计算
a = 'hello' + ' ' + 'world' #拼串

a = 10 - 5 #计算
a = 5 - True
a = a - 2 #用变量a的值减去2，然后再赋值给a
# a = 'hello' -'h' TypeError

a = 5 * 5

a = 10/5
a = 5 / 2
# a = 5 / 0 ZeroDivisionError: division by zero
a = 10 / 3

a = 10 // 3
a = 5 // 2

a = 2 ** 2
a = 10 ** 5
a = 16 ** 0.5 #求16的平方根

a = 10 % 5 # 0


print("a = ",a)

```

```python
# 赋值运算符
# 	赋值运算符可以将等号右边的值赋值给左侧的变量
# 	+= 	a+=5 相当于 a=a+5
#	-=
#	*=
#	/=
#	**=
#	//=
#	%=
a = 10
a += 5

print("a =",a)


```

```python
# 关系运算符
# 关系运算符用来比较两个值之间的关系，总会返回一个布尔值
# 如果关系成立，返回True，否则返回False
#	>	比较左侧值是否大于右侧值
#	>=	比较左侧值是否大于等于右侧值
#	<	比较左侧值是否小于右侧值
#	<=	比较左侧值是否小于等于右侧值
#	==	比较两个对象的值是否相当
#	!=	比较两个对象的值是否不相等
#	相等和不等比较的是对象的值，不是id
#	is 比较两个对象是否是同一个对象，比较的是对象的id
#	is not 比较两个对象是否不是同一个对象，比较的是对象的id


result = 30 > 20 # True
result = 30 < 20 # False
result = 10 >= 10 # True

result = 2 > True # True
# result = 2 > '1' TypeError : '>' not supported between instances of 'int' and 'str'

# 0032 > 0031
result = '2' > '1' # True
result = '2' > '11' # True

# 在Python中可以对两个字符串进行大于（等于）或小于（等于）的运算，
# 当对字符串进行比较时，实际上比较的是字符串的Unicode编码
# 比较两个字符串的Unicode编码时，是逐位比较的
# 利用该特性可以对字符串按照字母顺序进行排序，但是对于中文来说意义不是很大
# 注意：如果不希望比较两个字符串的Unicode编码，则需要将其转换为数字然后再比较
# 0061 > 0062
result = 'a' > 'b' # False
result = 'c' < 'd' # True
result = 'ab' > 'b' #False

result = 1 == 1 # True
result = 'hello' == 'hello' # True
result = 'abc' == 'bcd' # False
result = 'abc' != 'bcd' # True
result = 1 == True # True

result = 1 is True #False
result = 1 is not True #True

print('result = ',result)

```

```python
# 逻辑运算符
#	逻辑运算符主要用来做一些逻辑判断
#	not 逻辑非
#		not可以对符号右侧的值进行非运算
#			对于布尔值，非运算会对其进行取反操作，True变False，False变True
#			对于非布尔值，非运算会先将其转换成布尔值，然后再取反
#	and	逻辑与
#		and可以对符号两侧的值做与运算
#		只有在符号两侧的值都为True时，才会返回True，只要有一个False就会返回False
#		与运算是找False的
#		Python中的与运算是短路与，如果第一个值为False，则不再看第二个值
#	or	逻辑或
#		or可以对符号两侧的值做或运算
#		符号两侧的值只要有一个为True时，就会返回True，所有值都为False时，才返回False
#		或运算是找True的
#		Python中的或运算时短路或，如果第一个值为True，则不再看第二个值

a = True
a = not a #对a进行非运算

a = 1
a = ''
a = not a

print('a =',a)

result = True and True # True
result = True and False # False
result = False and True # False
result = False and False # False

# True and print('你猜我出来吗？') 第一个值是True，会看第二个值，所以print()会执行
# False and print('你猜我出来吗？')第一个值是False，不会看第二个值，所以print()不会执行

result = True or True # True
result = True or False # True
result = False or True # True
result = False or False # False

# True or print('你猜我出来吗？') 第一个值是True，不会看第二个值，所以print()不会执行
# False or print('你猜我出来吗？')第一个值是False，会看第二个值，所以print()会执行


print(result)

```

练习：尝试一下对布尔值进行三种逻辑运算，尝试对非布尔值进行三种逻辑运算，并观察返回的结果

```python
# 非布尔值的与或运算
# 	当我们队非布尔值进行与或运算时，Python会将其当做布尔值运算，最终会返回原值
#	与运算的规则
#		与运算时找False的，如果第一个值是False，则不看第二个值
#		如果第一个值是Flase，则直接返回第一个值，否则返回第二个值
#	或运算的规则
#		或运算是找True的，如果第一个值是True，则不看第二个值
#		如果第一个值是True，则直接返回第一个值，否则返回第二个值


# True and True
result = 1 and 2 # 返回2
# True and False
result = 1 and 0 # 0
# False and True
result = 0 and 1 # 0
# False and False
result = 0 and None # 0

# True or True
result = 1 or 2 #1
# True or False
result = 1 or 0 #1
# False or True
result = 0 or 1 #1
# False or False
result = 0 or None #None

print(result)

```

```python
# 条件运算符（三元操作符）
# 语法：语句1 if 条件表达式 else 语句2
# 执行流程：
#	条件运算符在执行时，会先对条件表达式进行求值判断
#		如果判断结果为True，则执行语句1，并返回执行结果
#		如果判断结果为False，则执行语句2，并返回执行结果

# print('你好') if True else print('Hello')

# print('你好') if False else print('Hello')

a = 10
b = 20

# print('a的值比较大!') if a > b else print('b的值比较大！') 
# 获取a和b之间的较大值
max = a if a > b else b

print(max)

```

练习：现在有a、b、c三个变量，三个变量中分别保存有三个数值，请通过条件运算符获取三个值得最大值

```python
a = 10
b = 20
c = 10

# 通过条件运算符获取三个值的最大值
# max = a if a > b else b
# max = max if max > c else c
max = a if (a > b and a > c) else (b if b > c else c) # 不推荐这么写
    

    
print(max)



```

```python
# 运算符的优先级
# 和数学中一样，在Python运算也有优先级，比如先乘除后加减
# 运算符的优先级可以根据优先级的表格来查询
#	在表格中位置越靠下的运算符优先级越高，优先级越高的越优先计算
#	如果优先级一样则自左向右运算
# 关于优先级的表格，你知道有这么个东西就行了，不要去记
# 在开发中如果遇到优先级搞不清楚的，则可以通过小括号来改变运算顺序
a = 1 + 2 * 3

# 一样  and高    or高
# 如果or的优先级高，或者两个运算符的优先级一样高，则需要先进行或运算，则运算结果是3
# 如果and的优先级高，则应该先计算与运算，则运算结果是1
a = 1 or 2 and 3 # 1

print(a)

```

```python
# 逻辑运算符（补充）
# 逻辑运算符可以连着使用
result = 1 < 2 < 3 # 相当于1 < 2 and 2 < 3
result = 10 < 20 > 15 # True

print(result)

```

