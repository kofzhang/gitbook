# 第七章 异常和文件

## 异常

程序在运行过程当中，不可避免的会出现一些错误，比如：

​	使用了没有赋值过的变量

​	使用了不存在的索引

​	除0

​	...

在这些错误在程序中，我们称其为异常。

程序运行过程中，一旦出现异常将会导致程序立即终止，异常以后的代码全部都不会执行！

## 处理异常

程序运行时出现异常，目的并不是让我们的程序直接终止！

Python是希望在出现异常时，我们可以编写代码对异常进行处理！



try语句

​	try:

​		代码块（可能出现错误的语句）

​	except 异常类型:

​		代码块（出现错误以后的处理方式）

​	else:

​		代码块（没出错时以后的语句）

​	finally:

​		代码块（该代码总会执行）

​	try是必须的，else语句有没有都行

​	except和finally至少有一个

可以将可能出错的代码放到try语句中，这样如果代码没有错误，则会正常执行，如果出现错误，则会执行except中的语句，这样我们就可以通过代码来处理异常，避免因为一个异常导致整个程序的终止



```python
print('hello')
try:
    # try中放置的是有可能出现错误的代码
	print(10/0)
    pass
except:
    # except中放置的是出错以后的处理代码
    print('哈哈哈，错误啦！')
    pass
else:
    print('程序正常执行没有错误')
    
print('nihao')
```

## 异常的传播

当在函数中出现异常时，如果在函数中对异常进行了处理，则异常不会再继续传播，如果函数中没有对异常进行处理，则异常会继续向函数调用处传播，如果函数调用处处理了异常，则不再传播，如果没有处理则继续向调用处传播，直到传递到全局作用域（主模块），如果依然没有处理，则程序终止，并显示异常信息

```python
def fn():
    print('Hello fn')
    print(10/0)
    pass

def fn2():
    print('Hello fn')
    fn()

fn2()
```

当程序运行过程中出现异常以后，所有的异常信息会被保存一个专门的异常对象中，而异常传播时，实际上就是异常对象抛给了调用处

比如：ZeroDivisionError类的对象专门用来表示除0的异常

​		NameError类的对象专门用来处理变量错误的异常

​		...

在Python中帮我们定义了很多异常信息类



```python
# 异常对象
print('异常出现前')

try:
    print(c)
	print(10/0)
except NameError:
    # 如果except后不跟任何的内容，则此时它会补货到所有的异常
    # 如果在except后跟着一个异常的类型，那么此时它只会捕获该类型的异常
    print('处理异常的代码')
except ZeroDivisionError:
    print('出现除0错误')
# Exceltion 是所有异常类的父类，所以如果except后跟的是Exception，他也会捕获到所有的异常
# 可以在异常类后面跟着一个as xx 此时xx就是异常对象
except Exception as e:
    print('未知异常',e)
finally :
    print('无论是否出现异常，该子句都会执行')
print('异常出现后')
```

## 抛出异常

可以使用raise 语句来抛出异常

```python
def add(a,b):
    # 如果a和b中有负数，就向调用处抛出异常
    if a<0 or b<0:
        # raise用于向外部抛出异常，后边可以跟一个异常类，或异常类的实例
        # 抛出异常的目的，告诉调用者这里调用时出现问题，希望你自己处理一下
        raise Exception('两个参数中不能有负数！')
        
        # 也可以通过if else 来代替异常的处理
        return None
    r=a+b
    return r

print(add(-123,456))
```

### 自定义异常类

```python
class MyError(Exception):
    pass
```

## 文件（file）

通过Python程序对计算机中的各种文件进行增删改查的操作

I/O （Input/Output）

操作文件的步骤：

1. 打开文件
2. 对文件进行各种操作（读、写），然后保存
3. 关闭文件

```python
# 打开文件
# open(file,...)
# 使用open函数来打开一个文件
# 参数：
#	file 要打开的文件的名字（路径）
# 返回值：
#	返回一个对象，这个对象就代表了当前打开的文件



# 创建一个变量，来保存文件的名字
# 如果目标文件和当前文件在同一级目录下，则直接使用文件名即可
file_name = 'demo.txt'

# 在windows系统使用路径时，可以使用/来代替\
# 或者可以使用\\来代替\\
# 或者也可以使用原始字符串
file_name = 'hello/demo.txt'
file_name = r'hello\demo.txt'

# 表示路径，可以使用..来返回一级目录
file_name = '../hello/demo.txt'

# 如果目标文件距离当前文件比较远，此时可以使用绝对路径
# 绝对路径应该从磁盘的根目录开始书写
file_name = r'C:\Users\kofzhang\Desktop\hello.txt'

file_obj = open(file_name) # 打开 file_name 对应的文件

```

```python
# 打开文件
file_name = 'demo.txt'

# 调用open()来打开文件
file_obj = open(file_name)

# 读取文件中的内容
# 当我们获取了文件对象以后，所有的对文件的操作都应该通过对象来进行
# read()方法，用来读取文件中的内容，它会将内容全部保存为一个字符串返回
content = file_obj.read()

print(content)

# 关闭文件
# 调用close() 方法来关闭文件
file_obj.close()


# with ... as 语句
with open(file_name) as file_obj:
    # 在with语句中可以直接使用file_obj来做文件操作
    # 此时这个文件只能在with中使用，一旦with结束则文件会自动close()
    print(file_obj.read())
    
    pass


file_name = 'hello'

try:
    with open(file_name) as file_obj:
        print(file_obj.read())
        pass
    pass
except FileNotFoundError:
    print(f'{file_name} 文件不存在')
```

```python
# 编码问题
file_name = 'hello'

try:
    # 调用open()来打开一个文件，可以将文件分成两种类型
    # 一种，是纯文本文件（使用utf-8等编码编写的文本文件
	# 一种，是二进制文件（图片、mp3、ppt等这些文件）
    # open()打开文件时，默认是以文本文件的形式打开的，但是open()文件的默认编码为None
    # 所以处理文本文件时，必须要指定文件的编码
    with open(file_name,encoding='utf-8') as file_obj:
        # 如果直接调用read()它会将文本文件的所有内容全部都读取出来
        # 如果要读取的文件较大的话，会一次性将文件的内容加载到内存中，容易导致内存溢出
        # 所以对于较大的文件，不要直接调用read()
        # help(file_obj.read)
        # read()可以接收一个size作为参数，该参数用来指定要读取字符的数量
        #	默认值为-1，它会读取文件中的所有字符
        #	可以为size指定一个值，这样read()会读取指定数量的字符
        #		每一次读取都是从上次读取到的位置开始读取的
        #		如果字符的数量小于size，则会读取剩余所有的字符
        #		如果已经读取到了文件的最后了，则会返回''空串
        print(file_obj.read())
        pass
    pass
except FileNotFoundError:
    print(f'{file_name} 文件不存在')
```

```python
# 读取大文件的格式
file_name = 'hello.txt'

try:
    with open(file_name,encoding='utf-8') as file_obj:
        # 定义一个变量，来指定每次读取的大小
        chunk=100
        # 创建一个循环来读取文件内容
        while True:
            # 读取chunk大小的内容
            content = file_obj.read(chunk)
            if not content:
                # 内容读取完毕
                break
            #输出内容
            print(content)
       
        pass
    pass
except FileNotFoundError:
    print(f'{file_name} 文件不存在')

```

```python
file_name = 'demo.txt'

with open(file_name,encoding='utf-8') as file_obj:
    # readline()
    # 该方法可以用来读取一行数据
    print(file_obj.readline(),end = '')
    
    # readlines()
    # 该方法用于一行一行的读取内容，它会一次性将读取到的内容封装到一个列表中返回
    r = file_obj.readlines()
    pprint.pprint(r[0])
    
    # 也是一行一行读取
    for t in file_obj:
        print(t)

```

```python
# 文件的写入
file_name = 'demo.txt'


# 使用open()打开文件时必须要指定打开文件所要做的操作（读、写、追加）
# 如果不指定操作类型，则默认是 读取文件，而读取文件时时不能向文件中写入的
# r 表示只读的
# w 表示是可写的，使用w来写入文件时，如果文件不存在会创建文件，如果文件存在则会截断文件
#	截断文件指删除原来文件中的所有内容
# a 表示追加内容，如果文件不存在会创建文件，如果文件存在则会向文件中追加内容
# x 用来新建文件，如果文件不存在则创建，存在则报错
# + 为操作符增加功能
# 	r+ 既可读又可写，文件不存在会报错
#	w+
#	a+
with open(file_name , 'a',encoding = 'utf-8') as file_obj:
    # write()来向文件中写入内容
    # 如果操作的是一个文本文件的话，则write()需要传递一个字符串作为参数
    # 该方法可以分多次向文件中写入内容
    # 写入完成以后，该方法会返回写入的字符的个数
    file_obj.write('Hello Hello How are you!')
    

```

```python
file_name = 'c:/Users/kofzhang/Desktop/aaa.flac'

# 读取模式
# t 读取文本文件（默认值）
# b 读取二进制文件
with open(file_name,'rb') as file_obj:
    # 读取文本文件时，size是以字符问单位的
    # 读取二进制文件时，size时以字节为单位的
    print(file_obj.read(100))
    
    # 将读取到的内容写出来
    # 定义一个新的文件
    new_name = 'aa.flac'
    
    with open(new_name,'wb') as new_obj:
        
        # 定义每次读取的大小
        chunk = 1024*100
        
        while True:
            
            # 从已有的对象中读取数据
            content = file_obj.read(chunk)

            # 内容读取完毕，终止循环
            if not content:
                break
            # 将读取到的数据写入到新对象中
            new_obj.write(content)

```

```python
# 读取文件的位置
with open('demo.txt','rb') as file_obj:
    print(file_obj.read(100))
    
    # seek() 可以修改当前读取的位置
    file_obj.seek(55)
    file_obj.seek(80,0)
    file_obj.seek(80,1)
    file_obj.seek(-1,2)
    # seek()需要两个参数
    #	第一个 是要切换到的位置
    # 	第二个 计算位置方式
    #		可选值：
    #			0 从头计算，默认值
    #			1 从当前位置计算
    #			2 从最后位置开始计算
    
    # tell() 方法用来查看当前读取的位置
    print('挡圈读取到了-->',file_obj.tell())

```

```python
# 文件的其他操作
import os
from pprint import pprint

# os.listdir() 获取指定目录的目录结构
# 需要一个路径作为参数，会获取到该路径下的目录结构，默认路径为. 当前目录
# 该方法会返回一个列表，目录中的每一个文件夹的名字都是列表中的一个元素

r = os.listdir()

# os.getcwd() 获取当前所在的目录
r = os.getcwd()

# os.chdir()切换当前所在的目录  作用相当于cd
os.chdir('c:/')

# 创建目录
# os.mkdir('aaa) # 在当前目录下创建一个名为aaa的目录

# 删除目录
# os.rmdi('abc')

open('aa.txt','w')
# 删除文件
os.remove('aa.txt')

os.rename('旧名字','新名字') # 可以对一个文件进行重命名，也可以用来移动一个文件
os.rename('aa.txt','C:/users/kofzhang/Desktop/bb.txt')

print(r)

```

