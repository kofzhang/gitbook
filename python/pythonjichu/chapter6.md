# 第六章 对象（Object）

## 什么是对象？

对象是内存中专门用来存储数据的一块区域。

对象中可以存放各种数据（比如：数字、布尔值、代码）

对象由三部分组成：

​	1.对象的标识（id)

​	2.对象的类型（type）

​	3.对象的值（value）

## 面向对象（oop）

Python是一门面向对象的变成语言

所谓的面向对象的语言，简单理解就是Python中的所有操作都是通过对象来进行的

面向过程的编程语言

- 面向过程指将我们的程序的逻辑分解为一个一个的步骤，通过对每个步骤的抽象，来完成程序

- 例子：

  ​	孩子上学

  ​		1.妈妈起床

  ​		2.妈妈上厕所

  ​		3.妈妈洗漱

  ​		4.妈妈做早饭

  ​		5.妈妈叫孩子起床

  ​		6.孩子上厕所

  ​		7.孩子洗漱

  ​		8.孩子吃饭

  ​		9.孩子背着书包上学校

  面向过程的变成思想将一个功能分解为一个一个小的步骤，通过完成一个个的小的步骤来完成一个程序

  但是这种方式编写的代码往往只适用于一个功能，如果要实现别的功能，往往要重新编写代码，可复用性比较低，并且难于维护

  这种编程方式，符合我们人类的思维，编写起来相对比较简单

面向对象的编程语言

​	面向对象的编程语言，关注的是对象，而不关注过程

​	例子：

​		1.孩他妈起床叫孩子上学

​	面向对象的变成思想，将所有的功能统一保存到对应的对象中

​		比如，妈妈功能保存到妈妈的对象中，孩子的功能呢刚保存到孩子对象中，要使用某个功能，直接找到对应的对象即可

​	这种方式编写的代码，比较容易阅读，并且比较易于维护，容易复用。

​	但是这种方式编写，不太符合常规的思维，编写起来稍微麻烦一点。

简单归纳一下，面向对象的思想

​	1.找对象

​	2.搞对象

## 类(class)

我们目前所学习的对象都是Python内置的对象

但是内置对象并不能满足所有的需求，所以我们在开发中经常需要自定义一些对象

类，简单理解它就相当于一个图纸，在程序中我们需要根据类来创建对象

类就是对象的图纸！

我们也称对象是类的实例。（instance）

如果多个对象是通过一个类创建的，我们称这些对象是一类对象。

像int() float() bool() str() list() dict()...这些都是类

a = int(10) #创建一个int类的实例，等价于 a = 10

我们自定义的类都需要使用大写字母开头，使用大驼峰命名法（帕斯卡命名法）来对类命名

```python
a = int(10) # 创建一个int类的实例
b = str('hello') # 创建一个string类的实例
print(a,type(a))
print(b,type(b))


# 定义一个简单的类
# 使用class关键字来定义类，语法和函数很像！
# class 类名([父类]):
#	代码块
class MyClass():
    pass

print(MyClass)

# 使用MyClass创建一个对象
#使用类来创建对象，就像调用一个函数一样

mc = MyClass() # mc就是通过MyClass创建的对象，mc是MyClass的实例
mc2 = MyClass()
# isinstance()用来检查一个对象是否是一个类的实例

result = isinstance(mc2,MyClass)
print(result)
print(mc,type(mc))

print(id(MyClass),type(MyClass))

# 现在我们通过MyClass这个类创建的对象都是一个空对象
# 也就是对象中实际上什么都没有，就相当于是一个空的盒子
# 可以向对象中添加变量，对象中的变量称为属性
# 语法：对象.属性名 = 属性值

mc.name = '孙悟空'
mc_2.name = '猪八戒'

print(mc_2.name)

```

类也是一个对象！

类就是一个用来创建对象的对象！

类是type类型的对象，定义类实际上就是定义了一个type类型的对象。



## 使用类创建对象的流程

1. 创建一个变量mc
2. 在内存中创建一个新对象
3. 将对象的id赋值给变量

## 类的定义

类和对象都是对现实生活中或程序中内容的抽象

实际上所有的事物都由两部分构成：

1. 数据（属性）
2. 行为（方法）

在类的代码块中，我们可以定义变量和函数，变量会成为该类实例的公共属性，所有的该类实例都可以通过 对象.属性名 的形式访问，函数会成为该类实例的公共方法，所有该类实例都可以通过 对象.方法名() 的形式访问

注意：

​	方法调用时，第一个参数由解析器自动传递，所以定义方法时，至少要定义一个形参

实例为什么能访问到类中的属性和方法

​	类中定义的属性和方法都是公共的，任何该类实例都可以访问

​	属性和方法查找的流程

​		当我们调用一个对象的属性时，解析器会先在当前对象中寻找是否含有该属性，如果有，则直接返回当前的对象的属性值，如果没有，则去当前对象的类对象中去寻找，如果有则返回类对象的属性值，如果没有则报错！

​	类对象和实例对象中都可以保存属性（方法）

​		如果这个属性（方法）时所有的实例共享的，则应该讲其保存到类对象中

​		如果这个属性（方法）时某个实例独有，则应该保存到实例对象中

​	一般情况下，属性保存到实例对象中，而方法保存到类对象中。

```python
# 尝试定义一个标识人的类
class Person :
    # 在类的代码块中，我们可以定义变量和函数
    # 在类中我们所定义的变量，将会成为所有的实例的公共属性
    # 所有实例都可以访问这些变量
    name = '孙悟空' # 公共属性，所有实例都可以访问
    
    
    # 在类中也可以定义函数，类中定义的函数，我们成为方法
    # 这些方法可以通过该类的所有实例来访问
    def say_hello(self) : 
        # 方法每次都调用时，解析器都会自动传递第一个实参
        # 第一个参数，就是调用方法的对象本身，
        #	如果是p1调的，则第一个参数都是p1对象
        # 	如果是p2调的，则第一个参数就是p2对象
        # 一般我们都会讲这个参数命名为self
        
        # say_hello()这个方法，可以显示如下格式的数据：
        # 	你好！我是xxx
        # 	在方法中不能直接访问方法类中的属性
        print('你好！我是%s' %self.name)

# 创建Person的实例
p1 = Person()
p2 = Person()

# 调用方法，对象.方法名()
# 方法调用和函数调用的区别
# 如果是函数调用，则调用时传几个参数，就会有几个实参
# 但是如果是方法调用，默认传递一个参数，所以方法中至少要定义一个形参
p1.say_hello()

p1.name = '猪八戒'
p2.name = '沙和尚'

print(p1.name)
print(p2.name)
```



```python
class Dog:
    '''
    	表示够的类
    '''
    def __init__(self,name,age,gender,height):
        self.name = name
        self.age = age
        self.gender = gender
        self.height = height
        pass
    def jiao(self):
        print('汪汪汪~~')
        pass
    def yao(self):
        print('我咬你~~')
        pass
    def run(slef):
        print('%s 快乐的奔跑者~'%self.name)
    pass

d = Dog('旺财',8,'male',30)
# 目前我们可以直接通过 对象.属性 的方式来修改属性的值，这种方式导致对象中的属性可以随意更改
#	非常的不安全，值可以任意修改，不论对错
# 现在我们就需要一种方式来增强数据的安全性
#	1.数据不能随意修改（我让你改你才能改，不让你改你就不能改）
#	2.属性不能修改为任意的值（年龄不能是负数）
d.name = '阿黄'

d.run()
```

```python
# 封装是面向对象的三大特性之一
# 封装指的是隐藏对象中一些不希望外部所访问到的属性或方法
# 如何隐藏一个对象中的属性？
#	- 将对象的属性名，修改为一个外部不知道的名字
# 如何获取（修改）对象中的属性？
#	- 需要提供一个getter和setter方法使外部可以访问到属性
#	- getter获取对象中的指定属性（get_属性名）
#	- setter用来设置对象的指定属性（set_属性名）
# 使用封装，确实增加了类的定义的复杂程度，但是它也确保了数据的安全性
# 	1.隐藏了属性名，使调用者无法随意的修改对象中的属性
#	2.增加了getter和setter，很好的控制了属性是否是只读的
#		如果希望属性时只读的，则可以直接去掉setter方法
#		如果希望属性不能被外部访问，则可以直接去掉getter方法
#	3.使用setter方法设置属性，可以增加属性的验证，确保数据是正确的
#	4.使用getter方法获取属性，使用setter方法设置属性
#		可以在读取属性和修改属性的同时做一些其他的处理
#	5.使用getter方法可以表示一些计算的属性

class Dog:
    '''
    	表示够的类
    '''
    def __init__(self,name，age):
        self.hidden_name = name
        self.hidden_age = age
        pass
    
    def say_hello(self):
        print('大家好，我是%s'%self.hidden_name)
    
    def get_name(self):
        return self.hidden_name
    
    def set_name(self,name):
        self.hidden_name = name
        
    def get_age(self):
        return self.hidden_age
    
    def set_age(self,age):
        if age > 0 :
            self.hidden_age = age
            pass
        pass
    
d = Dog('旺财')
d.name = '小黑'

d.set_name('小黑')
print(d.get_name())
```

```python
class Rectangle:
    '''
    	表示矩形的类
    '''
    def __init__(self,width,height):
        self.hidden_width = width
        self.hidden_height = height
        pass
    
    def get_width(self):
        return self.hidden_width
    
    def get_height(self):
        return self.hidden_height
    
    def set_width(self,width):
        self.hidden_width = width
        pass
    
    def set_height(self,height):
        self.hidden_height = height
        pass
    
    def get_area(self):
        return self.hidden_width * self.hidden_height
    
    pass

r = Rectangle(5,2)
r.set_width(10)
r.set_height(20)

print(r.get_area())
    
# 可以为对象的属性使用双下划线开头，__xxx
# 双下划线开头的属性，是对象的隐藏属性，隐藏属性只能在类的内部访问，无法通过对象访问
# 其实隐藏属性只不过是Python自动为属性改了一个名字
# 	实际上是将名字修改为了，_类名__属性名  比如 __name -> _Person__name
class Person:
    def __init__(self,name):
        self.__name = name
        pass
    
    def get_name(self):
        return self.__name
    
    def set_name(self,name):
        self.__name = name
        pass
    pass

o = Person('孙悟空')
# __开头的属性时隐藏属性，无法通过对象访问
# p.__name = '沙和尚'

print(p.get_name())

# 使用__开头的属性，实际上依然可以在外部访问，所以这种方式我们一般不用
#	一般我们会将一些私有属性（不希望被外部访问的属性）以_开头
#	一般情况下，使用_开头的属性都是私有属性，没有特殊需要不要修改私有属性

class Person:
    def __init__(self,name):
        self._name = name
        pass
    
    def get_name(self):
        return self._name
    
    def set_name(self,name):
        self._name = name
        pass
    pass
```

```python
class Person:
    def __init__(self,name):
        self._name = name
        pass
    
    # property装饰器，用来将一个get方法，转换为对象的属性
    # 添加为property装饰器以后，我们就可以像调用属性一样使用get方法
    # 使用property装饰的方法，必须和属性名是一样的
    @property
    def name(self):
        print('get方法执行了')
        return self._name
    
    # setter方法的装饰器：@属性名.setter
    @name.setter
    def name(self,name):
        print('setter方法调用了')
        self._name = name
    
    
    pass

p = Person('猪八戒')

p.name = '孙悟空'

print(p.name)
```

```python
# 继承

# 定义一个类 Animal（动物）
# 	这个类中需要两个方法：run()  sleep()
class Animal:
    def run(self):
        print('动物会跑')
        pass
    
    def sleep(self):
        print('动物睡觉')
        pass
    
    pass

# 定义一个类 Dog（狗）
#	这个类中需要三个方法：run() sleep() bark()
# 有一个类，能够实现我们需要的大部分功能，但是不能实现全部功能
# 如何能让这个类来实现全部的功能呢？
#	①直接修改这个类，在这个类中添加我们需要的方法
#		修改起来会比较麻烦，并且会违反OCP原则
#	②直接创建一个新的类
#		创建一个新的类比较麻烦，并且需要大量的进行复制粘贴，会出现大量的重复性代码
#	③直接从Animal类中来继承它的属性和方法
#		继承是面向对象三大特性之一
#		通过继承我们可以使一个类获取到其他类中的属性和方法
#		在定义类时，可以在类名后的括号中指定当前类的父类（超类、基类、super）
#			子类（衍生类）可以直接继承父类中的所有的属性和方法
# 通过继承可以直接让子类获取到父类的方法或属性，避免编写重复性代码，并且也符合OCP原则
#	所以我们经常需要通过继承来对一个类进行扩展
class Dog(Animal):
    def bark(self):
        print('汪汪汪')
        pass
    pass

class Hashiqi(Dog):
    def fasha(self):
        print('我是一只傻傻的哈士奇')
        pass
    pass


d = Dog()

d.run()
d.sleep()
    
d.bark()

result = isinstance(d,Dog)
r = isinstance(d,Animal)
print(r)

# 在创建类时，如果省略了父类，则默认父类为object
#	object是所有类的父类，所有类都继承自object

# issubclass检查一个类是否是另一个类的子类
print(issubclass(Dog,Animal))
print(issubclass(Dog,object))

# isinstance()用来检查一个对象是否是一个类的实例
#	如果这个类时这个对象的父类，也会返回True
#	所有的对象都是object的实例
print(isinstance(print,object))


```

```python
# 重写
class Animal:
    def run(self):
        print('动物会跑')
        pass
    
    def sleep(self):
        print('动物睡觉')
        pass
    
    pass

class Dog(Animal):
    def bark(self):
        print('汪汪汪')
        pass
    
    def run(slef):
        print('狗跑')
        pass
    
    pass

# 如果在子类中如果有和父类同名的方法，则通过子类实例去调用方法时，会调用子类的方法二不是父类的方法，这个特点我们成为叫做方法的重写（覆盖，override）
# 创建DOg类的实例
d = Dog()

d.run()


# 当我们调用一个对象的方法时，会优先去当前对象中寻找是否具有该方法，如果有则直接调用，如果没有，则去当前对象的父类中寻找，如果父类中有则直接调用父类中的方法，如果没有，则去父类的父类中寻找，以此类推，直到找到object，如果依然没有，则报错
class A(object):
    def test(self):
        print('AAA')
        pass
    pass

class B(A):
    def test(self):
        print('BBB')
        pass
    pass

class C(B):
    def test(self):
        print('CCC')
        pass
    pass

# 创建c的实例
c = C()
c.test()
```

```python
class Animal:
    
    def __init__(self,name):
        self._name = name
    
    def run(self):
        print('动物会跑')
        pass
    
    def sleep(self):
        print('动物睡觉')
        pass
    
    @property
    def name(self):
        return self._name
    
    @name.setter
    def name(self,name):
        self._name = name
        pass
    pass

# 父类中的所有放大都会被子类继承，包括特殊方法
class Dog(Animal):
    
    def __init__(self,name,age):
        # self._name = name 希望可以直接调用父类的__init__来初始化父类中定义的属性
        # Animal.__init__(self,name) 不要这样使用
        # super()可以用来获取当前类的父类
        #	并且通过super()返回对象调用父类方法时，不需要传递self
        super().__init__(self,name)
        self._age = age
        pass
    
    def bark(self):
        print('汪汪汪')
        pass
    
    def run(slef):
        print('狗跑')
        pass
    
    @property
    def age(self):
        return self._age
    
    @age.setter
    def age(self,age):
        self._age = age
        pass
    
    
    pass

d = Dog('旺财',18)
d.name = '小黑'
print(d.name)

```

```python
# 多重继承
class A(object):
    def test(self):
        print('AAA')
        pass
    pass

class B(A):
     def test(self):
        print('B的test')
        pass
    def test2(self):
        print('BBB')
        pass
    pass

# 在Python中是支持多重继承的，也就是我们可以为一个类同时制定多个父类
#	可以在类名的()后边添加多个类，来实现多重继承
#	多重继承，会使子类同时拥有多个父类，并且会获取到所有父类中的方法
# 在开发中没有特殊的情况，应该尽量避免使用多重继承，因为多重继承会让我们的代码过于复杂
# 如果多个父类中有同名的方法，则会先在第一个父类中寻找，然后找第二个，然后找第三个
#	前边的会覆盖后边的父类的方法
#
class C(A,B):
    pass

# 类名.__bases__  这个属性可以用来获取当前类的所有父类
print(C.__bases__)

c = C()
c.test()
c.test2()

```

```python
# 多态是面向对象的三大特征之一
# 多态从字面上理解是多种形态
# 狗（狼狗、藏獒、哈士奇、古牧。。。）
# 一个对象可以以不同的形态去呈现

# 定义两个类
class A:
    def __init__(self,name):
        self._name = name
        pass
    
    @property
    def name(self):
        return self._name
    
    @name.setter
    def name(self,name):
        self._name = name
        pass
    
    pass

class B:
    def __init__(self,name):
        self._name = name
        pass
    
    @property
    def name(self):
        return self._name
    
    @name.setter
    def name(self,name):
        self._name = name
        pass
    
    pass

a = A('孙悟空')
b = B('猪八戒')

# 定义一个函数
# 对于say_hello()这个函数来说，只要对象中含有name属性，它就可以作为参数传递
#	这个函数并不会考虑对象的类型，只要有name属性即可
def say_hello(obj):
    print('你好 %s'%obj.name)
    pass

# 在say_hello2中我们做了一个类型检查，也就是只有obj是A类型的对象时，才可以正常使用
#	其他类型的对象偶读无法使用该函数，这个函数就违反了多态
# 违反了多态的函数，只适用于一种类型的对象，无法处理其他类型对象，这样导致函数的适应性非常的差
# 注意，像isinstance()这种函数，在开发中一般是不会使用的！
def say_hello2(obj):
    # 做类型检查
    if isinstance(obj,A):        
    	print('你好 %s'%obj.name)
    pass

say_hello(a)

# 鸭子类型
# 如果一个东西，走路像鸭子，叫声像鸭子，那么它就是鸭子

# len()
# 之所以一个对象能通过len()来获取长度，是因为对象中具有一个特殊方法__len__
# 换句话说，只要对象中具有__len__特殊方法，就可以通过len()来获取它的长度
l = [1,2,3]
s = 'hello'

print(len(l))

class B:
    def __init__(self,name):
        self._name = name
        pass
    
    def __len__(self):
        return 10
    
    @property
    def name(self):
        return self._name
    
    @name.setter
    def name(self,name):
        self._name = name
        pass
    
    pass

b= B('猪八戒')
print(len(b))

# 面向对象的三大特征：
#	封装
#		确保对象中的数据安全
#	继承
#		保证了对象的可扩展性
#	多态
#		保证了程序的灵活性

```

```python
# 定义一个类
class A(object):
    
    # 雷属性
    # 实例属性
    # 类方法
    # 实例方法
    # 静态方法
   
    
    # 类属性，直接在类中定义的属性时类属性
    # 	雷属性可以通过类或类的实例访问到
    #	但是雷属性只能通过类对象来修改，无法通过实例对象修改
    count = 0
    
    def __init__(self):
        # 实例属性，通过实例对象添加的属性属于实例属性
        #	实例属性只能通过实例对象来访问和修改，类对象无法访问修改
        self.name = '孙悟空'
        pass
    
    # 实例方法
    #	在类中定义，以self为第一个参数的方法都是实例方法
    #	实例方法在调用时，Python会将调用对象作为self传入
    #	实例方法可以通过实例和类去调用
    #		当通过实例调用时，会自动将当前调用对象作为self传入
    #		当通过类调用时，不会自动传递self，此时我们必须手动传递self
    def test(self):
        print('这是test方法')
    
    #类方法
    # 在类内部使用@classmethod 来修饰的方法属于类方法
    # 类方法的第一个参数时cls，也会被自动传递，cls就是当前的类对象
    #	类方法和实例方法的区别，实例方法的第一个参数时self，而类方法的第一个参数是cls
    #	类方法可以通过类去调用，也可以通过实例调用，没有区别
    @classmethod
    def test_2(cls):
        print('这是test_@方法，他是一个类方法')
    
    # 静态方法
    # 在类中使用 @staticmethod 来修饰的方法属于静态方法
    # 静态方法不需要制定任何的默认参数，静态方法可以通过类和实例去调用
    # 静态方法，基本上是一个和当前类无关的方法，它只是一个保存到当前类中的函数
    # 静态方法一般都是一些工具方法，和当前类无关
    @staticmethod
    def test_3():
        print('test_3执行了')
    
    pass

a = A()
# 实例属性，通过实例对象添加的属性属于实例属性
a.count = 10
print(A.count)
print(a.count)

#a.test()等价于A.test(a)

#A.test_2()等价于a.test_2()

A.test_3()
a.test_3()

```

```python
# 垃圾回收
# 就像我们生活中会产生垃圾一样，程序在运行过程当中也会产生垃圾
# 程序运行过程中产生的垃圾会影响到程序的运行的运行性能，所以这些垃圾必须被及时清理
# 没用的东西就是垃圾
# 在程序中没有被引用的对象就是垃圾，这种垃圾对象过多以后会影响到程序的运行的性能
#	所以我们必须进行及时的垃圾回收，所谓的垃圾回收就是将垃圾对象从内存中删除
# 在Python中有自动的垃圾回收机制，它会自动将这些没有被引用的对象删除
# 	所以我们不用手动手动处理垃圾回收

class A:
    def __init__(self):
        self.name = 'A类'
        pass
    
    # del是一个特殊方法，它会在对象呗垃圾回收钱调用
    def __del__(self):
        print('A()对象呗删除了~~~',self)
    pass

a = A()

b = a #又使用一个变量b，来引用a对应的对象

print(a.name)

a = None  # 将a设置为了None，此时没有任何的变量对A()对象进行引用，它就变成了垃圾



input('回车键退出')

```

```python
# 特殊方法，也成为魔术方法
# 特殊方法都是使用__开头和结尾
# 特殊方法一般不需要手动调用，需要在一些特殊情况下自动执行

# 定义一个Person类

class Person(object):
    
    def __init__(self,name,age):
        self.name = name
        self.age = age
        pass
    
    # __str__()这个特殊方法会在尝试将对象转换为字符串的时候调用
    # 它的作用可以用来指定对象转换为字符串的结果
    def __str__(self):
        return 'Pserson [name=%s , age=%d]'%(self.name,self.age)
    
    # __repr__这个特殊方法会在对当前对象使用repr()使用时调用
    # 它的作用是指定对象在‘交互模式’中直接输出的结果
    def __repr__(self):
        return 'Hello'
    
    #__lt__ 小于
    #__le__ 小于等于
    #__eq__ 等于
    #__ne__ 不等于
    #__gt__ 大于
    #__ge__ 大于等于
    
    # __gt__会在对象做大于比较的时候调用，该方法的返回值将会作为比较的结果
    # 它需要两个参数，一个self表示当前对象，other表示和当前对象比较的对象
    # self>other
    def __get__(self,other):
        return self.age > other.age
    
    # __len__获取对象的长度
    
    # __bool__
    # 可以通过bool来指定转换规则
    def __bool__(self):
        return self.age > 17
    
    #object.__add__(self, other)
	#object.__sub__(self, other)
	#object.__mul__(self, other)
	#object.__matmul__(self, other)
	#object.__truediv__(self, other)
	#object.__floordiv__(self, other)
	#object.__mod__(self, other)
	#object.__divmod__(self, other)
	#object.__pow__(self, other[, modulo])
	#object.__lshift__(self, other)
	#object.__rshift__(self, other)
	#object.__and__(self, other)
	#object.__xor__(self, other)
	#object.__or__(self, other)
    pass

	
# 创建两个Person类的实例

p1 = Person('孙悟空',18)
p1 = Person('猪八戒',28)


# 打印p1
# 当我们打印一个对象时，实际上打印的是对象中的特殊方法__Str__()的返回值
# print(p1) # <__main__.Person object at 0xXXXXXXXX>

print(p1)


print(p1>p2)

```

```python
# 模块（module）
# 模块化，模块化指将一个完整的程序分解为一个一个小的模块
#	通过将模块组合，来搭建出一个完整的程序
# 不采用模块化，同意将所有的代码编写到一个文件中
# 采用模块化，将程序分别编写到多个文件中
# 	模块化的优点：
#		①方便开发
#		②方便维护
#		③模块可以复用

# 在Python中一个py文件就是一个模块，要想创建模块，实际上就是创建一个python文件
# 注意：模块名要符合标识符的规范

# 在一个模块中引入外部模块
# ① import 模块名（模块名，就是python文件的名字，注意不要py）
# ② import 模块名 as 模块别名
# 	可以引入同一个模块多次，但是模块的实例只会创建一个
#	import可以在程序的任意位置调用，但是一般情况下，import语句一般都会统一卸载开头
#	在每一个模块内部都有一个__name__属性，通过这个属性可以获取到模块的名字
#	__name__属性值为__main__的模块是主模块，一个程序中只会有一个主模块
#		主模块就是我们直接通过python执行的模块

import test_module as test

print(test)
print(__name__)


# 也可以只引入模块中的部分内容
# 语法 from 模块名 import 变量，变量....
from m import Person
from m import test
#from m import Person,test
from m import *  # 引入到模块中所有内容，一般不会使用

# 也可以为引入的变量使用别名
# 语法 ： from模块名 import 变量 as 别名
from m import test2 as new_test2

p1 = Person()
test()


# 总结
# import xxx
# import xxx as yyy
# from xxx import yyy,zzz,fff
# from xxx import *
# from xxx import yyy as zzz


```

```python
#filename = test_module.py
print('我是一个模块')

```

```python
import m


# 访问模块中的变量： 模块名.变量名
print(m.a,m.b)

m.test()

p = m.Person()

print(p.name)


```



```python
# m.py
# 可以在模块中定义变量，在模块中定义的变量，在引入模块后，就可以直接使用了
a = 10
b = 20

# 添加了_的变量，只能在模块内部使用，在通过import * 引入时，不会引入_开头的变量
_c = 30

# 可以在模块中定义函数，同样通过模块访问到

def test():
    print('test')
    pass

# 也可以定义类
class Person:
    def __init__(self):
        self.name = '孙悟空'
		pass
    pass

# 编写测试代码，这部分代码，只又当当前文件作为主模块的时候才需要执行
#	而当模块被其他模块引入时，不需要执行的，此时我们就必须要检查当前模块是否是主模块
if __name == '__main__':
    test()

        
        
        

```

```python
# 包  Package
# 包也是一个模块
# 当我们模块中代码过多时，或者一个模块需要被分解为多个模块时，这是就需要使用到包
# 普通的模块就是一个py文件，而包是一个文件夹
# 	包中必须要有一个 __init__.py 文件，这个文件可以包含有包中的主要内容

from hello import a,b
print(a.c)
print(b.d)

# __pycache__ 是模块的缓存文件
# py代码在执行前，需要被解析器先转换为机器码，然后再执行
# 	所以在使用模块（包）时，也需要将模块的代码先转换为机器码然后再交由计算机执行
# 	而为了提高程序运行的性能，python会在变异过一次以后，将代码保存到一个缓存文件中
#	这样在下次加载这个模块（包）时，就可以不再重新编译而是直接加载缓存中编译好的代码即可

```

```python
# Python的标准库
# 开箱即用
# 为了实现开箱即用的思想，Python中为我们提供了一个模块的标准库
# 在这个标准库中，有很多强大的模块我们可以直接使用
#	并且标准库会随Python的安装一同安装
# sys模块，它里面提供了一些变量和函数，使我们可以获取到Python解析器的信息
#	或者通过函数来操作Python解析器
# 引入sys模块
import sys

# pprint 模块它给我们提供了一个方法 pprint() 该方法可以用来对打印的数据做简单的格式化
import pprint

# sys.argv
# 获取执行代码时，命令行中所包含的参数
# 该属性时一个列表，列表中保存了当前命令的所有参数
print(sys.argv)

# sys.modules
# 获取当前程序中引入的所有模块
# modules是一个字典，字典的key是模块的名字，value是模块对象
pprint.pprint(sys.modules)


# sys.path
# 它是一个列表，列表中保存的是模块的搜索路径
pprint.pprint(sys.path)


# sys.platform
# 表示当前Python运行的平台
print(sys.platform)

# sys.exit()
# 函数用来退出程序
sys.exit()

# os模块让我们可以对操作系统进行访问
import os

# os.environ
# 通过这个属性可以获取到系统的环境变量
pprint.pprint(os.environ)

# os.system()
# 可以用来执行操作系统的名字
os.system('dir')

```

