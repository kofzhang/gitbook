# 第四章 序列

## 列表（list）

列表是Python中的一个对象

对象（object）就是内存中专门用来存储数据的一块区域

之前我们学习的对象，像数值，它只能保存一个单一的数据

列表中可以保存多个有序的数据

列表的使用：

​	1.列表的创建

​	2.操作列表中的数据



练习：

​	创建一个列表，在列表中保存你最好的5个朋友的名字，然后分别通过索引来获取每一个朋友的名字

```python
# 创建列表，通过[] 来创建列表
my_list = [] # 创建了一个空列表
# print(my_list,type(my_list))

# 列表存储的数据，我们称为元素
# 一个列表中可以存储多个元素，也可以在创建列表时，来指定列表中的元素
my_list = [10] # 创建一个只包含一个元素的列表

# 当向列表中添加多个元素时，多个元素之间使用逗号隔开
my_list = [10,20,30,40,50] # 创建了一个包含有5个元素的列表

# 列表中可以保存任意的对象
my_list = [10,'hello',True,None,[1,2,3],print]

# 列表中的对象都会按照插入的顺序存储到列表中，第一个插入的对象保存到第一个位置，第二个放置到第二个位置
my_list = [10,20,30,40,50]

# 我们可以通过索引（index）来获取列表中的元素
# 索引是元素在列表中的位置，列表中的每一个元素都有一个索引
# 索引是从0开始的整数，列表第一个位置索引为0，第二个位置索引为1，以此类推

#通过索引获取列表中的元素
# 语法：my_list[索引]


print(my_list[0])

# 如果使用的索引超过了最大的范围，会抛出异常
# print(my_list[5]) IndexError: list index out of range

#获取列表的长度，列表中元素的个人
# len()函数，通过该函数可以获取列表的长度
# 获取到的长度的值，是列表的最大索引+1
print(len(my_list))
```



```python
# 切片
# 切片指从现有列表中，获取一个字列表
# 创建一个列表，一般创建列表时，变量的名字会使用复数
stus = ['孙悟空','猪八戒','沙和尚','蜘蛛精','白骨精']

# 列表的索引可以是负数
# 如果索引是负数，则从后向前获取元素，-1表示倒数第一个，-2表示倒数第二个，以此类推
print(stus[-1])

# 通过切片获取指定的元素
# 语法：列表[起始：结束]
# 	通过切片获取元素时，会包括起始位置的元素，不会包括结束位置的元素
# 	做切片操作时，总会返回一个新的列表，不会影响原来的列表
#	起始和结束位置的索引都可以省略不写
#	如果省略结束位置，则会一直截取到最后
#	如果省略开始位置，则会从第一个元素开始截取
#	如果开始和结束位置全部省略，则相当于创建了一个列表的副本
print(stus[1:4])

# 语法：列表[起始：结束：步长]
# 步长表示，每次获取元素的间隔，默认值是1
# 步长不能是0，但是可以是负数   ValueError: slice step cannot be zero
# 如果是负数，则会从列表的后部向前边取元素
print(stus[0:5:1])
```

```python
# 通用操作
# 创建列表
stus = ['孙悟空','猪八戒','沙和尚','蜘蛛精','白骨精']

# + 和 *
# + 可以将两个列表拼接为一个列表
my_list [1,2,3] + [4,5,6]

# * 可以将列表重复指定的次数
my_list = [1,2,3] * 5

# in 和not in
# in用来检查指定元素是否存在于列表中
#	如果存在，返回True，否则返回False
# not in用来检查指定元素是否不再列表中
#	如果不再，返回True，否则返回False
print('沙和尚' in stus)
print('牛魔王' in stus)
print('牛魔王' not in stus)

# len() 获取列表中的元素的个数

# min() 获取列表中的最小值
# max() 获取列表中的最大值

arr = [10,1,2,5,100,77]
print(min(arr),max(arr))

# 两个方法(method)，方法和函数基本上是一样的，只不过方法必须通过对象.方法()的形式调用
# xxx.print() 方法实际上就是和对象关系紧密的函数
# s.index() 获取指定元素在列表中第一次出现时的索引
#	如果要获取列表中没有的元素，会抛出异常 ValueError
#	index()的第二个参数，表示查找的起始位置，第三个参数，表示查找的结束位置
print(stus.index('孙悟空',3,6))
# s.count()
# 统计指定元素在列表中出现的次数
print(stus.count('沙和尚'))
```

## 序列（sequence）

序列是Python中最基本的一种数据结构

数据结构指计算机中数据存储的方式

序列用于保存一组有序的数据，所有的数据在序列中都有一个唯一的位置（索引），并且序列中的数据会按照添加的顺序来分配索引

序列的分类

​	可变序列

​		列表（list）

​	不可变序列

​		字符串（str）

​		元祖（tuple）

```python
# 创建一个列表
stus = ['孙悟空','猪八戒','沙和尚','蜘蛛精','白骨精']

print('修改前：',stus)
# 修改列表中的元素
# 直接通过索引来修改元素

stus[0] = 'sunwukong'
stus[2] = '哈哈'

# 通过del来删除元素
del stus[2] # 删除索引为2的元素
print('修改后：',stus)


# 通过切片来修改列表
# 在给切片进行赋值时，只能使用序列
stus[0:2] = ['牛魔王','红孩儿','二郎神']
stus[0:0] = ['牛魔王'] #向索引为0的位置插入元素

# 当我们设置了步长时，序列中元素的个数比如和切片中元素的个数一致
stus[::2] = ['牛魔王','红孩儿','二郎神']

# 通过切片来删除元素
del stus[0:2]
del stus[::2]
stus[1:3] = []

print('修改后：',stus)


# 以上操作，只适用于可变序列
s = 'hello'
# s[1] = 'a' 不可变序列，无法通过索引来修改
# 可以通过list()函数将其他的序列转换为list
s = list(s)
print(s[::2])
```

```python
# 列表的方法
stus = ['孙悟空','猪八戒','沙和尚']
print('原列表：',stus)

# append()
# 向列表的最后添加一个元素
# stus[3] = '唐僧'   不可以这样添加
stus.append('唐僧')

# insert()
# 向列表的指定位置插入一个元素
# 参数：
# 	1.要插入的位置
#	2.要插入的元素
stus.insert(2,'唐僧')


# extend()
# 使用心得序列来扩展当前序列
# 需要一个序列作为参数，它会将该序列中的元素添加到当前列表中
stus.extend(['唐僧','白骨精'])
stus += ['唐僧','白骨精']

# clear()
# 清空序列
stus.clear()

# pop()
# 根据索引删除并返回指定元素
result = stus.pop(2) #删除索引为2的元素
result = stus.pop() #删除最后一个元素
print('result=',result)

# remove()
# 删除指定值得元素，如果相同值得元素有多个，只会删除第一个
stus.remove('猪八戒')

# reverse()
# 用来翻转列表
stus.reverse()
print('修改后：',stus)
# sort()
# 排序，对列表中的元素进行排序，默认是升序排列
# 参数reverse=True,降序排列
my_list = list('akljsdfkjasdf')
my_list.sort()
print(my_list)


```

```python
# 遍历列表，指的就是将列表中的所有元素取出来
# 创建列表
stus = ['孙悟空','猪八戒','沙和尚','蜘蛛精','白骨精']

# 遍历列表
print(stus[0])
print(stus[1])
print(stus[2])
print(stus[3])
print(stus[4])

# 通过while循环来遍历列表
i = 0
while i < len(stus) :
    print(stus[i])
    i += 1
    pass

# 通过for循环来遍历列表
# 语法：
#	for 变量 in 序列 ：
#		代码块
# for循环的代码块会执行多次，序列中有几个元素就会执行几次
# 每执行一次就会将序列中的一个元素赋值给变量
# 所以我们可以通过变量，来获取列表中的元素
for s in stus :
    print(s)
    pass

```

## EMS (Employee Manager System 员工管理系统) 练习

做命令行版本的员工管理系统

功能：

​	1.查询

​		显示当前系统当中的所有员工

​	2.添加

​		将员工添加到当前系统中

​	3.删除

​		将员工从系统当中删除

​	4.退出

​		退出系统

员工信息要保存到哪里？列表，在系统中应该有一个列表，专门用来保存员工信息

```python
# EMS练习
# 显示系统的欢迎信息
print('='*20,'欢迎使用员工管理系统','='*20)
# 创建一个列表，用来保存员工的信息，员工的信息以字符串的形式统一保存到列表中
emps = ['孙悟空\t18\t男\t花果山']
# 创建一个循环
while True :
    # 显示用户的选项
    print('请选择要做的操作：')
    print('\t1.查询员工')
    print('\t2.添加员工')
    print('\t3.删除员工')
    print('\t4.退出系统')
    user_choose = input('请选择[1-4]：')
  	# 打印分割线
    print('-'*62)
    #根据用户的选择来做相关的操作
    if user_choose == '1' :
        #查询员工
        #打印表头
        print('\t序号\t姓名\t年龄\t性别\t住址')
        # 创建一个变量，来表示员工的序号
        n = 1
        #显示员工信息
        for emp in emps :
            print(f'\t{n}\t{emp}')
            n += 1
        pass
    elif user_choose == '2' :
        #添加员工
        # 获取要添加员工的信息
        emp_name = input('请输入员工姓名：')
        emp_age = input('请输入员工年龄：')
        emp_gender = input('请输入员工性别：')
        emp_address = input('请输入员工住址')
        emp=f'{emp_name}\t{emp_age}\t{emp_gender}\t{emp_address}'
        
        # 显示提示
        print('以下员工将要添加到系统中')
        print('-'*62)
        print('姓名\t年龄\t性别\t住址')
        print(emp)
        print('-'*62)
        user_confirm = input('是否确认操作[Y/N]：')
        
        if user_confirm == 'y' or user_confirm == 'yes':
            emps.append(emp)
            print('添加成功！')
            pass
        else :
            print('该操作已被取消！')
        pass
    elif user_choose == '3' :
        #删除员工
        #获取要删除的员工的序号
        del_num = int(input('请输入要删除的员工的序号：'))
        # 判断序号是否有效
        if 0 < del_num <= len(emps):
            del_i = del_num - 1
            # 显示提示
            print('以下员工将从系统中删除')
            print('-'*62)
            print('\t序号\t姓名\t年龄\t性别\t住址')
           	print(f'\t{del_num}\t{emps[del_i]}')
            print('-'*62)
            user_confirm = input('该操作不可恢复，是否确认操作[Y/N]：')
            # 判断
            if user_confirm  == 'y' or user_confirm == 'yes' :
                # 删除元素
                emps.pop(del_i)
                # 显示提示
                print('员工已被删除。')
                pass
            else :
                print('操作已取消！')
                pass
            pass
        
        else :
            # 输入有误
            print('您的输入有误，请重新操作！')
        pass
    elif user_choose == '4' :
        # 退出
        input('感谢使用！再见！点击回车键退出！')
        break
        pass
    else :
        print('您的输入有误，请重新选择！')
        pass
    # 打印分割线
    print('-'*62)
```

```python
# range()是一个函数，可以用来生成一个自然数的序列
r = range(5) # 生成一个这样的序列[0,1,2,3,4]

# 该函数需要三个参数
#	1.起始位置（可以省略，默认是0）
#	2.结束位置
#	3.步长（可以省略，默认是1）

r = range(0,10,2)
r = range(10,0,-1)
print(list(r))


# 通过range（）可以创建一个指定次数的for循环
# for()循环除了创建方式以外，其余都和while一样
# 	包括else、包括break continue都可以在for循环中使用
#	并且for循环使用也更加简单

for i in range(10):
    print(i)

```

练习：将之前使用while循环做的练习，再使用for循环完成一次！

```python
# 元组 tuple
# 元组是一个不可变的序列
# 它的操作的方式基本上和列表是一直的
# 所以你再操作元组时，就把元组当成是一个不可变的列表就可以
# 一般当我们希望数据不改变时，就使用元组，其余情况都使用列表

# 粗行间元组
# 使用()来创建元组
my_tuple = () # 创建了一个空元组
print(my_tuple,type(my_tuple))

my_tuple = (1,2,3,4,5) #创建了一个5个元素的元组
# 元组是不可变对象，不能尝试为元组中的元素重新赋值
# my_tuple[3] = 10 TypeError
print(my_tuple[3])

# 当元组不是空元祖时，括号可以省略
# 如果元组不是空元祖，它里面至少要有一个逗号
my_tuple = 10,20,30,40
my_tuple = 40,
print(my_tuple , type(my_tuple))


my_tuple = 10,20,30,40

# 元组的解包（解构）
# 解包就是将元组当中每一个元素都赋值给一个变量
a,b,c,d = my_tuple
print('a=',a)
print('b=',b)
print('c=',c)
print('d=',d)

a = 100
b = 300
print(a,b)
# 交换a 和b的值，这时我们就可以利用元组的解包
a,b=b,a
print(a,b)

my_tuple = 10,20,30,40

# 在对一个元组进行解包时，变量的数量必须和元组中的元素数量一致
# 也可以在变量前边添加一个*，这样变量将会获取元组中所有剩余的元素
a,b,*c = my_tuple

a , *b,c = my_tuple
a,b,*c = [1,2,3,4,5,6]
a,b,*c = 'hello world'
#不能同时出现两个或以上的*变量
# *a,*b,c = my_tuple SyntaxError
print(a,b)
print('c=' ,c)


```

## 可变对象

每个对象中都保存了三个数据：

​	id（标识）

​	type（类型）

​	value（值）

列表就是一个可变对象

​	a = [1,2,3]

a[0] = 10（改对象）

​	这个操作是在通过变量去修改对象的值

​	这种操作不会改变变量所指向的对象

​	当我们去修改对象时，如果有其他变量也指向了该对象，则修改也会在其他变量中体现

a = [4,5,6]（改变量）

​	这个操作是在给变量重新赋值

​	这种操作会改变变量所指向的对象

​	为一个变量重新赋值时，不会影响其他变量

一般只有在为变量赋值时才是修改变量，其余的都是修改对象

```python
# 可变对象
a = [1,2,3]
print('修改前：',a,id(a))

#通过索引修改列表
a[0] = 10
print('修改后；',a,id(a))

# 为变量重新赋值
a = [4,5,6]
print('再次修改后：',a,id(a))


a = [1,2,3]
b=a
b[0] = 10

print('a',a,id(a))
print('b',b,id(b))

b = [10,2,3]
print('a',a,id(a))
print('b',b,id(b))


# ==  !=  is    is not
# ==  != 比较的是对象的值是否相等
# is    is not 比较的是对象的id是否相等（比较两个对象是否是同一对象）

a = [1,2,3]
b = [1,2,3]
print(a,b)
print(id(a),id(b))
print(a == b) # a 和b 的值相等，使用==会返回True
print(a is b) # a和b不是同一个对象，内存地址不同，使用is会返回False




```



## 字典（dict）

字典属于一种新的数据结构，称为映射（mapping）

字典的作用和列表类似，都是用来存储对象的容器

列表存储数据的性能很好，但是查询数据的性能很差

在字典中每一个元素都有一个唯一的名字，通过这个唯一的名字可以快速的查找到指定的元素

在查询元素时，字典的效率是非常快的

在字典中可以保存多个对象，每个对象都会有一个唯一的名字

​	这个唯一的名字，我们称其为键（key）

​	这个对象，我们称其为值（value）

​	所以字典，我们也称为键值对（key-value）结构

​	每个字典中都可以有多个键值对，而每一个键值对我们称其为一项（item）

```python
# 字典
# 使用 {}来创建字典
d = {} #创建了一个空字典

# 创建一个包含有数据的字典
# 语法：
#	{key:value,key:value,key:value}
# 	字典的值可以是任意对象
#	字典的key可以是任意的不可变对象（int、str、bool、tuple ...}但是一般我们使用str
#		字典的键是不能重复的，如果出现重复的，后面的会覆盖前面的
d = {'name':'孙悟空','age':18,'gender':'男'}

print(d,type(d))


# 需要根据键来获取值
print(d['name'],d['age'],d['gender'])

# 如果使用了字典中不存在的键，会报错
print(d['hello']) # KeyError: 'hello'



```



```python
# 字典的使用
# 创建字典
# 使用{}
# 语法：{k1:v1,k2:v2,k3:v3}

# 使用 dict()函数来创建字典
d = dict(name='孙悟空',age=18,gender='男') # 每一个参数都是一个键值对，参数名就是键，参数就是值（这种方式创建的字典，key都是字符串）
# 也可以将一个包含有双值子序列的序列转换为字典
# 双值序列，序列中只有两个值，[1,2] ('a',3) 'ab'
# 子序列，如果序列中的元素也是序列，那么我们就称这个元素为子序列
# [(1,2),(3,5)]
d = dict([('name','孙悟饭'),('age',18)])
print(d,type(d))

# len() 获取字典中键值对的个数
print(len(d))

# in   检查字典中是否包含指定的键   
# not in  检查字典中是否不包含指定的键
print('name' in d)

# 获取字典中的值，根据键来获取值
# 语法：d[key]
print(d['name'])

n = 'name'
print(d[n])

# 通过[]来获取值时，如果键不存在，会抛出KeyError
# get(key[, default])该方法用来根据键来获取字典中的值
# 	如果获取的键在字典中不存在，会返回None
# 	也可以指定一个默认值，来作为第二个参数，这样获取不到值时将会返回默认值
# print(d.get('name'))
# print(d.get('hello','默认值'))

#修改字典
# d[key] = value 如果key存在则覆盖，不存在则添加
d['name'] ='sunwukong' #修改字典的key-value

d['address'] = '花果山' # 向字典中添加key-value
print(d)

# setdefault(key[, default])可以用来向字典中添加key-value
# 	如果key存在，则返回key的值，不会对字典做任何操作
#	如果key不存在，则向字典中添加这个key，并设置value
result = d.setdefault('name','猪八戒')
print('result = ',result)
print(d)

# update([other])
# 将其他字典中的key-value添加到当前字典中
# 如果有重复的key，则后边的会替换到当前的
d = {'a':1,'b':2,'c':3}
d2 = {'d':4,'e':5,'f':6,'a':7}

d.update(d2)
print(d)

#删除，可以使用del来删除字典中的key-value
del d['a']
del d['b']

# popitem()
# 随机删除字典中的一个键值对，一般都会删除最后一个键值对
# 	删除之后，它会将删除的key-value作为返回值返回
#	返回的是一个元祖，元祖中有两个元素，第一个元素是删除的key，第二个是value
# 当使用popitem()时，会抛出异常
d.popitem()
result = d.popitem()
print('result=', result)

# pop(key[,default]) 
# 根据key删除字典中的key-value
# 会将被删除的value返回！
# 如果删除不存在的key，会抛出异常
#	如果制定了默认值，再删除不存在的key时，不会报错，而是直接返回默认值
result = d.pop('a')
result = d.pop('z','这是默认值')

# del ['z'] z不存在，报错

# clear()用来清空字典
d.clear()
print(d)

# copy()
# 该方法用于对字典进行浅复制
# 复制以后的对象，和原对象是独立的，修改一个不会影响另一个
# 注意，浅复制会简单复制对象内部的值，如果值也是一个可变对象，这个可变对象不会被复制
d = {'a':1,'b':2,'c':3}
d2 = d.copy()
# d['a'] = 100
d = {'a':{'name':'孙悟空','age':18},'b':2,'c':3}
d2 = d.copy()
d2['a']['name'] = '猪八戒'
print('d = ',d,id(d))
print('d2 = ',d2,id(d2))


```

```python
# 遍历字典
# keys() 该方法会返回字典的所有的key
# 	该方法会返回一个序列，序列中保存有字典的所有的键
d = {'name':'孙悟空','age':18,'gender':'男'}

#通过遍历keys()来获取所有的键
for k in d.keys() :
    print(k,d[k])
print(d.keys())

# values()
# 该方法会返回一个序列，序列中保存有字典的所有的值
for v in d.values() :
    print(v)
    
# items()
# 该方法会返回字典中所有的项
# 它会返回一个序列，序列中包含有双值子序列
# 双值分别是，字典中的key和value
print(d.items())

for k,v in d.items() :
    print(k,'=',v)

```

## 集合（set）

集合和列表非常相似

不同点：

​	1.集合中只能存储不可变对象

​	2.集合中存储的对象是无序的（不是按照元素的插入顺序保存）

​	3.集合中不能出现重复的元素

```python
# 集合
# 创建集合
# 使用{}来创建集合
s = {1,2,3,4}

# 使用set()来创建集合
s = set() #空集合
# 可以通过set()将序列和字典转换为集合
s = set([1,2,3,4,5,1,1,2,3,4,5])
s = set('hello')
s = set({'a':1,'b':2,'c':3}) #使用set()将字典转换为集合时，只会包含字典中的键

# 创建集合
s = {'a','b',1,2,3}

# 使用in和not in来检查集合中的元素
print('a' in s)
# 使用len()来获取集合中元素的数量
print(len(s))

# add()向集合中添加元素
s.add(10)
s.add(30)

# update()将一个集合中的元素添加到当前集合中
#	update()可以传递序列或字典作为参数，字典只会使用键
s2 = set('hello')
s.update(s2)
s.update((10,20,30,40,50))
s.update({10:'ab',20:'bc',100:'cd',1000:'ef'})

# pop()随机删除并返回一个集合中的元素
result = s.pop()
print(result)

# remove()删除集合中的指定元素
s.remove(100)

# clear() 清空集合
s.clear()

# copy()对集合进行浅复制

print(s , type(s))

```

```python
# 集合的运算，不会影响原来的集合，而是返回一个运算结果
# 创建两个集合
s = {1,2,3,4,5}
s2 = {3,4,5,6,7}

# & 交集运算
result = s & s2  #{3,4,5}

# | 并集运算
result = s | s2 # {1,2,3,4,5,6,7}

# - 差集
result = s - s2 # {1,2}

# ^ 异或集  获取只在一个集合中出现的元素
result = s ^ s2 # {1,2,6,7}

# <= 检查一个集合是否是另一个集合的子集
# 如果一个集合中的元素全部都在另一个集合中出现，那么这个集合就是另一个集合的子集,另一个集合就是这个集合的超集
a = {1,2,3}
b = {1,2,3,4,5}
result = a <= b

# < 检查一个集合是否是另一个集合的真子集
# 如果超集b中含有子集a中的所有元素，并且b中还有a中没有的元素，则b是a的真超级，a是b的真子集

result  = {1,2,3} <{1,2,3} # false

# >= 检查一个集合是否是另一个的超集
# > 检查一个集合是否是另一个的真超集

print('result = ',result)

```

