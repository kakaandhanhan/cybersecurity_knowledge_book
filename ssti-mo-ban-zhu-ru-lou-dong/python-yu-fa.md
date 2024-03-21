---
description: 本来以为可以逃过这个，毕竟这个学期刚好在学python，但是知识点摆在这里，得先自己学了。这里就讲一下python的语法。
layout:
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 📣 Python语法

## （1）输出函数print

### ①语法结构：

#### Ⅰ.直接输出单一内容

```python
print('输出内容'）
print("输出内容")
```

输出内容用单引号，双引号都可以，或者用三个单引号，三个双引号也都可以。或者直接用对象输出。

```python
a = 100
b = 200
print(a)
print(b)
print('hello world')
print("hello world")

```

<figure><img src="../.gitbook/assets/image (200).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.一次输出多个内容

如果我们想将几个对象一行输出，那么我们可以用

```python
print(对象1，对象2，对象3，…………）
```

这样输出的对象在同一行，并且每一个对象都用一个空格隔开。

```python
a = 100
b = 200
print(a, b, 'hello world')

```

<figure><img src="../.gitbook/assets/image (201).png" alt=""><figcaption></figcaption></figure>



#### Ⅲ.输出ascii码和他们对应的字符

这里我们要介绍两个函数一个是chr（），一个时ord（）

> chr（）：python的内置函数，返回unicode码位为i的字符的字符串格式，比如，chr（97）就返回'a'
>
> ```python
> chr（i）
> ```

> ord（）：python的内置函数，对表示但是unicode字符的字符串，返回代表他的unicode的整数。比如ord（'a')返回的是97，他是chr（）的逆函数。
>
> ```python
> ord(c)
> ```



如果我们想要得到一个字符的ascii码或者是某个ascii码对应的字符，可以用

```python
print(chr(i))
print(ord(c))
```

直接得到他们的结果输出，第一个得到字符，第二个得到数字。

```python
print(chr(101))
print(ord('c'))

```

<figure><img src="../.gitbook/assets/image (202).png" alt=""><figcaption></figcaption></figure>

#### Ⅳ.将内容输出到文件

这里需要补充open函数。

> open（）：打开file并返回对应的file object。file是文件要打开的路径。mode是要给文件打开的模式，比如r是以文本模式读取，w是写入（如果文件已存在，就将其清空），b是二进制模式，+是打开用于更新。所以
>
> * 'r':是默认模式，打开文件用于读取文本，
> * 'w+'/'w+b':将打开文件并清空内容
> * 'r+'/'r+b':打开文件但不清空内容。
>
> ```python
> open(file,mode='r',encoding=None,errors=None,newline=None)
> ```

这里展示如何打开文件并且输出信息到文件中。

```python
fp = open('node.txt', 'w')
print('hello world', file=fp)
fp.close()

```



<figure><img src="../.gitbook/assets/image (205).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/image (204).png" alt=""><figcaption></figcaption></figure>



#### Ⅴ.输出连接字符串

我们可以用+去连接字符串，然后把他们输出。

```python
print('字符串1‘+’字符串2‘+.....);
```

比如说：

```python
print('hello' + 'world' + 'hanhan')

```

<figure><img src="../.gitbook/assets/image (206).png" alt=""><figcaption></figcaption></figure>



***

## （2）输入函数input（）

### ①语法结构

```python
x=input（'提示文字’）
```

在没有进行强制转换的情况下，无论输入的数据是什么，x的数据类型都是字符串类型。

举个例子。

```python
name = input('请输入你的名字')
print('hello world' + name)
```

<figure><img src="../.gitbook/assets/image (207).png" alt=""><figcaption></figcaption></figure>

如果我们想要接收除了字符串以外的数据，我们可以使用强制转换。

```python
int(input('提示文字'))
float(input('提示文字'))
```

举个例子

```python
name = int(input('请输入你的年龄'))
print(type(name))
print(name)

```

<figure><img src="../.gitbook/assets/image (208).png" alt=""><figcaption></figcaption></figure>



***

## （3）注释

注释应该不用我再解释什么叫注释了吧。

### Ⅰ.单行注释

用`#来进行单行注释`

```python
#注释文字
```

举个例子

```python
# this is mc guangguan
name = int(input('请输入你的年龄'))
print(type(name))
print(name)

```

<figure><img src="../.gitbook/assets/image (209).png" alt=""><figcaption></figcaption></figure>





### Ⅱ.多行注释

我们用三个单引号`'''****** '''`，或者三个双引号`"""*******"""`来进行多行注释，

```python
"""
注释文字
"""



'''
注释文字
'''
```

举个例子

```python
'''
this
is
mc
guagnguan
'''

name = int(input('请输入你的年龄'))
print(type(name))
print(name)

"""
speed
no
1
"""
```

<figure><img src="../.gitbook/assets/image (210).png" alt=""><figcaption></figcaption></figure>

### Ⅲ.中文注释

其实这个是针对python2的版本，python3已经不用了。就是对于python2的时候，如果你需要输入中文，并且不能出现乱码的话就要用，但是s不用了，我们就提一嘴。



***

## （4）代码缩进

python中没有大括号，所以用代码缩进来表示不同的层次，一般是两个空格，四个空格，一个tab这种。

{% hint style="info" %}
但是一个python文件里面只能出现一种缩进方式，不能混用。
{% endhint %}



***

## （5）保留字和标识符

保留字就是python中被赋予特定意义的一些单词，这些保留字_**不能**_作为变量，函数，类，模块和其他对象的名称来使用。

<figure><img src="../.gitbook/assets/image (211).png" alt=""><figcaption></figcaption></figure>

标识符的命名规则和c语言一样的，就不多说了



***

## （6）变量

python中的变量不要被定义说是什么类型，他可以直接通过赋值去换他的类型。

这里介绍两个函数id（）和type（）

> id(object):返回对象的内存地址。

> type(object):返回object的类型。



举个例子。

```python
name = 'hanhan'
print(type(name))
name =123
print(type(name))
name = 12.4
print(type(name))
```

<figure><img src="../.gitbook/assets/image (214).png" alt=""><figcaption></figcaption></figure>

```python
name = 'hanhan'
print(id(name))
name =123
print(id(name))
name = 12.4
print(id(name))
```

<figure><img src="../.gitbook/assets/image (215).png" alt=""><figcaption></figcaption></figure>





***

## （7）数值类型

也不想多说，int，float，double，boolean，这里多了一个complex（复数，就是高中学的实部，虚部那个玩意）



***

## （8）字符串类型

字符串序列：连续的字符序列。从左到右是0，1，2，3，4，这样标号。这种标号其实是一种检索，被称为索引

### ①单行字符串，多行字符串

前面提到过，不多说，就是多行字符串，可以用/连接或者`""" """表示`

### ②转义字符

<figure><img src="../.gitbook/assets/image (216).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
使转义字符失效的字符，r或R
{% endhint %}



### ③切片

切片是字符串中某个子串或者区间的索引。这个索引可以从左到右，也可以从右到左。

这里有网课的图直接贴了。

<figure><img src="../.gitbook/assets/image (217).png" alt=""><figcaption></figcaption></figure>

#### Ⅰ.语法结构

字符串或字符串变量\[N:M]，这个N到M是从N开始，到M结束，但是<mark style="color:red;">不包括M</mark>

所以如果我们要表示上面图的红色框里面的，就应该是\[2:7]或者\[-8:-3]。

并且我们的左边或者右边没有的话，那么我们就是到边界值

我们可以举个例子

```python
name = 'hello world hanhan'
print(name[6:15])
print(name[:15])
print(name[6:])
print(name[-12:-5])
```

<figure><img src="../.gitbook/assets/image (219).png" alt=""><figcaption></figcaption></figure>



### ④字符串操作

字符串有拼接，复制，判断之类的操作

#### Ⅰ.拼接

我们用`+`来拼接字符串

```
字符串1+字符串2
```

举个例子

```python
a = 'hello'
b = 'world'
c = 'hanhan'
print(a + b + c)

```

<figure><img src="../.gitbook/assets/image (220).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.复制

我们用字符串\*n或者n\*字符串，来将字符串复制n次。

```
字符串*n
n*字符串
```

举个例子

```python
a = 'hello'
b = 'world'
c = 'hanhan'
print((a + b + c) * 5)

```

<figure><img src="../.gitbook/assets/image (221).png" alt=""><figcaption></figcaption></figure>



#### Ⅲ.判断

判断一个字符串x是不是在另一个字符串s里面，是否是他的子串。我们用in

```
x in s
```

如果是就返回True，如果不是就是False

```python
a = 'hello'
b = 'world'
c = 'hanhan'
d = (a + b + c) * 5
print((a + b + c) * 5)
print(a in d)

```

<figure><img src="../.gitbook/assets/image (222).png" alt=""><figcaption></figcaption></figure>



***

## （9）布尔类型

就是True和False。

```
布尔类型的True和False是首字母大写，不然就是表示字符串。
```



***

## （10）数据类型转换

这个类型转换有隐式转换和显式转换。

### ①利用函数强制转换

<figure><img src="../.gitbook/assets/image (223).png" alt=""><figcaption></figcaption></figure>

### ②算术运算转换

#### Ⅰ.除法

```python
a = 10
b = 3
c = 10/3
print(type(c))
print(c)

```

<figure><img src="../.gitbook/assets/image (224).png" alt=""><figcaption></figcaption></figure>



***

## (11)eval函数

> eval()用于去掉字符串最外侧的引号，并按照python语句方式执行去掉引号后的字符串，eval函数常常和input一起使用

### ①语法结构

```
变量 = eval(字符串）
```

{% hint style="info" %}
让我想起来了php里面的eval函数。
{% endhint %}

举个例子

```python
a = 'c + d'
c = 2345
d = 5353
print(eval(a))

```

<figure><img src="../.gitbook/assets/image (225).png" alt=""><figcaption></figcaption></figure>

除此之外，我们还可以用这个函数去把字符串转换为int，真是让人开眼了。

```python
a = '35353'
print(eval(a))
print(type(eval(a)))

```

<figure><img src="../.gitbook/assets/image (226).png" alt=""><figcaption></figcaption></figure>

没想到吧，还能把字符串变成对象。

```python
hello = 'hanhan'
print(eval('hello'))
```

<figure><img src="../.gitbook/assets/image (227).png" alt=""><figcaption></figcaption></figure>



***

## （12）运算符

## 1.算数运算符

<figure><img src="../.gitbook/assets/image (228).png" alt=""><figcaption></figcaption></figure>

这个就太简单了，我们就不说了。

### ①优先级

<figure><img src="../.gitbook/assets/image (229).png" alt=""><figcaption></figcaption></figure>

### ②多种赋值方式

python有多种赋值方式，不像c语言赋值方式那么单调。哈哈哈哈哈，拉踩了。

#### Ⅰ.链式赋值

就是我们说的连等

```python
a = b = c = 100
print(a)
print(b)
print(c)
```

<figure><img src="../.gitbook/assets/image (230).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.系列解包赋值

就是一个等号，两边按照顺序一个一个赋值

```python
a, b, c = 100, 200, 300
print(a)
print(b)
print(c)
```

<figure><img src="../.gitbook/assets/image (231).png" alt=""><figcaption></figcaption></figure>

## 2.比较运算符

<figure><img src="../.gitbook/assets/image (232).png" alt=""><figcaption></figcaption></figure>

不多说，还是一样的。



## 3.逻辑运算符

<figure><img src="../.gitbook/assets/image (233).png" alt=""><figcaption></figcaption></figure>

也不多说。



## 4.位运算符

这些和php，c语言一样的。

<figure><img src="../.gitbook/assets/image (234).png" alt=""><figcaption></figcaption></figure>



***

## (13)选择结构

### ①if

和c语言一样，就是格式不一样。这里就只是介绍一下格式。

```python
if 表达式:
    语句块
    
    
if not 表达式:
    语句块
```

{% hint style="info" %}
这里需要注意，空，0都会代表False。
{% endhint %}

### ②if-else

```python
if 表达式:
    语句块
else:
    语句块

```

### ③if-elif-else

```python
if 表达式:
    语句块
elif 表达式:
    语句块
elif 表达式:
    语句块
elif 表达式n:
    语句块
else:
    语句块
```

这里就举一个总体的例子

```python
score = eval(input('请输入您的分数'))
#多分支结构
if score <0 or score >100:
    print('成绩有误\n')
elif 0 <= score < 60:
    print('E\n')
elif 60 <= score < 70:
    print('D\n')
elif 70 <= score < 80:
    print('C\n')
elif 80 <= score < 90:
    print('B\n')
else:
    print('A\n')
```

<figure><img src="../.gitbook/assets/image (235).png" alt=""><figcaption></figcaption></figure>

***

## （14）循环结构

### ①for

#### Ⅰ.for-in

```python
for 循环变量 in 遍历对象:
    语句块
```

举个例子

```python
s = 0
for i in range(1, 11):
    s += 1
print(s)
```

<figure><img src="../.gitbook/assets/image (236).png" alt=""><figcaption></figcaption></figure>



#### Ⅱ.for-else

```python
for 循环变量 in 变量对象:
    语句块
else:
    语句块
```

这个就是for语句执行完了以后，就执行else的语句。

举个例子

```python
s = 0
for i in range(1, 11):
    s += 1
else:
    print(s)
    
```

<figure><img src="../.gitbook/assets/image (237).png" alt=""><figcaption></figcaption></figure>

### ②while

Ⅰ.while

```python
while 表达式:
    语句块
```

举个例子

```python
answer = input('今天晚上要上课吗?y/n')
while answer == 'y':
    print('好好学习天天向上')
    answer = input('今天晚上要上课吗?y/n')
```

<figure><img src="../.gitbook/assets/image (238).png" alt=""><figcaption></figcaption></figure>





Ⅱ.while-else

```python
while 表达式:
    语句块
else:
    语句块
```

举个例子

```python
answer = input('今天晚上要上课吗?y/n')
while answer == 'y':
    print('好好学习天天向上')
    answer = input('今天晚上要上课吗?y/n')
else:
    print('小伙子不行啊')
```

<figure><img src="../.gitbook/assets/image (239).png" alt=""><figcaption></figcaption></figure>

### ③break

break用于跳（退）出循环结构，通常与if一起搭配使用

```python
while 表达式1:
    执行代码
    if 表达式2:
        break
```

举个例子

```python
s = 0
i = 1
while i < 11:
    s += 1
    if s > 5 :
        print('s大于5')
        break
    i += 1

print('success')

```

<figure><img src="../.gitbook/assets/image (240).png" alt=""><figcaption></figcaption></figure>



### ④continue

用于跳过本次循环的后续代码，继续执行下一次循环操作。

```python
while 表达式1：
        执行代码
        if 表达式2：
                continue
```

举个例子

```python
s = 0
i = 1
while i < 11:
    s += 1
    if s > 5 :
        print('s大于5')
        continue
    i += 1

print('success')

```

<figure><img src="../.gitbook/assets/image (241).png" alt=""><figcaption></figcaption></figure>



***

## （15）空语句pass

pass是python中的保留字，在语法结构中起到占位符的作用，使语法结构完整，不报错。一般可用在if，for，while，函数的定义，类的定义中。

```python
if True :
    pass
```

<figure><img src="../.gitbook/assets/image (242).png" alt=""><figcaption></figcaption></figure>



***

## （16）序列和索引



前面其实说过了这里就不多说了，直接贴图

<figure><img src="../.gitbook/assets/image (243).png" alt=""><figcaption></figcaption></figure>





***

## （17）切片

这里也带有前面讲的一部分。 [#qie-pian](python-yu-fa.md#qie-pian "mention") 这里进行一些补充和完善

### ①语法结构：

```python
序列[start: end: step]
```

start是切片的开始索引（包含），end是切片的结束索引（不包含），step是步长（默认为1）。

<figure><img src="../.gitbook/assets/image (244).png" alt=""><figcaption></figcaption></figure>

### ②例子

```python
s = 'hello world'

s1 = s[0: 10:2]
print(s1)

print(s[: 5:])

print(s[0::1])

```

<figure><img src="../.gitbook/assets/image (245).png" alt=""><figcaption></figcaption></figure>



***

## （18）序列操作

<figure><img src="../.gitbook/assets/image (246).png" alt=""><figcaption></figcaption></figure>

直接上例子

```python
s = 'helloworld'
print('e在helloworld中存在吗', ('e' in s))
print('v在helloworld中存在吗', ('v' in s))

print('e在helloworld中不存在吗', ('e' not in s))
print('v在helloworld中不存在吗', ('v' not in s))

print('len():', len(s))
print('max():', max(s))
print('min():', min(s))

print('s.index():', s.index('o'))
print('s.count()', s.count('l'))
```

<figure><img src="../.gitbook/assets/image (247).png" alt=""><figcaption></figcaption></figure>



***

## （19）列表

### ①列表类型

<figure><img src="../.gitbook/assets/image (248).png" alt=""><figcaption></figcaption></figure>



### ②列表创建

<figure><img src="../.gitbook/assets/image (249).png" alt=""><figcaption></figcaption></figure>

如果我们用list函数创建的话，生成的结果是里面的每一个对象（就是如果是字符串，那么列表中就是每一个字符；如果是一系列数字，就是一个一个的数字）

我们这里举个例子。

```python
# 直接用格式创建
list1 = ['hello', 'wolrd', 23, 45, 67]
print(list1)
# 用函数创建
list2 = list('hello,world')
# 请注意list函数创建出来的结果
print(list2)
list3 = list(range(1, 10, 2))
print(list3)

print(list1 + list2 + list3)

```

<figure><img src="../.gitbook/assets/image (250).png" alt=""><figcaption></figcaption></figure>

列表也能执行我们在序列里面提到的一些操作，比如一些函数，len（），max（），min（），in，not int 这种，也可以执行＋和\*的操作。但是max和min和len只能在列表中的元素是一种类型才能使用，不然就会报错。一定要注意这一点，因为本人写的代码就因为这个事情报错了。想骂人。

比如

```python
list1 = ['hanhan', 'hello', 34, 56.7, True]
list2 = ['hanhan', 'hello', 'abc']
print(list1 * 2)
print(min(list2))
print(len(list2))
print('hanhan' in list1)

```

<figure><img src="../.gitbook/assets/image (251).png" alt=""><figcaption></figcaption></figure>



### ③列表的遍历

#### Ⅰ.enumereate()函数

这里要扩展一个函数enumerate（）。这个英文意思就是枚举的意思。

它的用法就是

```python
for index,item in enumerate(lst):
    输出index和item
```

这个



#### Ⅱ.for 利用元素去遍历列表

就是直接遍历列表里面的元素，每一次遍历得到的值都将赋值给item

```python
list1 = ['hanhan', 'hello', 34, 56.7, True]
list2 = ['hanhan', 'hello', 'abc']

for item in list1:
    print(item)


```

<figure><img src="../.gitbook/assets/image (252).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.for利用索引来遍历列表

这个也有限制，要求了数据得是一样的类型，不然len（）函数没法使用。

```python
list1 = ['hanhan', 'hello', 34, 56.7, True]
list2 = ['hanhan', 'hello', 'abc']

for i in range(0, len(list2)):
    print(list2[i])


```

<figure><img src="../.gitbook/assets/image (253).png" alt=""><figcaption></figcaption></figure>

#### Ⅲ.使用enumerate（）函数

```python
list1 = ['hanhan', 'hello', 34, 56.7, True]
list2 = ['hanhan', 'hello', 'abc']

for index, item in enumerate(list1):
    print(index,item)


```

<figure><img src="../.gitbook/assets/image (4) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="info" %}
这里的index是序号，这个序号的开始值是可以修改的。我们可以把开始值修改成1，那么他的第一个序号就变成了1.
{% endhint %}

```python
list1 = ['hanhan', 'hello', 34, 56.7, True]
list2 = ['hanhan', 'hello', 'abc']

for index, item in enumerate(list1, start=1):
    print(index,item)


```

<figure><img src="../.gitbook/assets/image (1) (1) (1).png" alt=""><figcaption></figcaption></figure>

这个start=可以省略不写，直接写1就行。



### ④列表特有操作

列表可以增删改查

<figure><img src="../.gitbook/assets/image (2) (1) (1).png" alt=""><figcaption></figcaption></figure>



我们将一一举例进行分析

```python
list1 = ['hello', 'world', 'hanhan', 234]
print('原列表', list1, id(list1))

# 增加元素操作
list1.append('sql')
print('增加元素之后', list1, id(list1))

# 插入元素，在index位置上插入元素x
list1.insert(1, 'love you')
print('插入元素之后', list1)

# 列表元素的删除操作
list1.remove('hello')
print('删除元素之后', list1, id(list1))

# 使用pop（index）弹出某个元素并且删除
list1.pop(1)
print('弹出元素之后', list1)

# 列表反向
list1.reverse()
print('列表反向后', list1)

# 列表的拷贝
new_list2 = list1.copy()
print('拷贝列表的新列表', new_list2)

# 清楚列表中所有元素
list1.clear()
print('清除元素后', list1, id(list1))

```

<figure><img src="../.gitbook/assets/image (3) (1) (1).png" alt=""><figcaption></figcaption></figure>



### ⑤列表排序

<figure><img src="../.gitbook/assets/image (4) (1) (1).png" alt=""><figcaption></figcaption></figure>

排序需要保证列表里面的对象的数据类型一致。并且对字符排序是先大写后小写。

对sort的使用，sort是内置方法，不是函数，函数是sorted。这个要分清楚。这里就和我最开始错误的代码相关了，sort是对列表本身进行操作。但是sorted（）函数是会产生一个新的列表对象了，我们需要用另外一个新的列表去接收这个。

#### Ⅰ.sort

```python
list1 = ['A', 'hanhan', 'a', 'cgt', 'TCD']
print('原列表为', list1)

# 输出升序排序后的列表
list1.sort()
print('升序排序后的列表为', list1)

# 降序排序后的列表
list1.sort(reverse=True)
print('降序排序后的列表为', list1)

# 忽略大小写的排序
list1.sort(key=str.lower)
print('忽略大小写后的排序为', list1)


```

<figure><img src="../.gitbook/assets/image (5) (1).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.sorted()

```python
list1 = ['A', 'hanhan', 'a', 'cgt', 'TCD']
print('原列表为', list1)

# 输出升序排序后的列表
list2 = sorted(list1)
print('升序排序后的列表为', list2)

# 降序排序后的列表
list3 = sorted(list1, reverse=True)
print('降序排序后的列表为', list3)

# 忽略大小写的排序
list4 = sorted(list1, key=str.lower)
print('忽略大小写后的排序为', list4)


```

<figure><img src="../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>



### ⑥列表生成式

除了可以手动添加元素，还可以用生成式添加元素。

<figure><img src="../.gitbook/assets/image (7) (1).png" alt=""><figcaption></figcaption></figure>

举个例子

```python
import random
list1 = [item for item in range(1, 10)]
print(list1)

list2 = [item * item for item in range(1, 11)]
print(list2)

list3 = [random.randint(1, 100) for i in range(1, 11)]
print(list3)

list4 = [i for i in range(10) if i%2==0]
print(list4)



```

<figure><img src="../.gitbook/assets/image (8) (1).png" alt=""><figcaption></figcaption></figure>



### ⑦二维列表

一个列表中又嵌套了列表就是二维列表

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

我们接下来就以图中的例子来复现代码。

```python
list1 = [
    ['城市', '环比', '同比'],
    ['北京', 102, 203],
    ['上海', 104, 504],
    ['深圳', 100, 39]
]
print(list1)

# 遍历二位列表
for row in list1:
    for col in row:
        print(col, end='\t')
    print('\n')

# 用列表生成式生成一个4行5列的二维列表
list2 = [[j for j in range(5)] for i in range(4)]
print(list2)

```

<figure><img src="../.gitbook/assets/image (1) (1).png" alt=""><figcaption></figcaption></figure>



***

## （20）元组

### ①元组创建

<figure><img src="../.gitbook/assets/image (2) (1).png" alt=""><figcaption></figcaption></figure>

不可变序列，就是确定了就确定了，不能更改，所以他没有增删改的操作，只能查看。

并且对于一些序列的判断操作，对元组来说也是可行的。

{% hint style="info" %}
对于用tuple（）中把list中的元素创建为元组，并不是把list当做元组的一个对象，而是把list中的元素当成元组的对象。+
{% endhint %}

```python
t = ('hello', [10, 20, 30], 'python', 30)
print(t)

t2 = tuple('helloworld')
print(t)

t3 = tuple([10, 20, 30, 40])
print(t3)

# 判断操作
print('10在元组中是否存在', (10 in t))
print('10在元组中是否不存在', (10 not in t))
print('最大值', max(t3))
print('最小值', min(t3))
print('len为', len(t))
print('t.index:', t.index(30))
print('t.count:', t.count(30))

# 如果元组中只有一个元素
t4 = (20,)
print(t4)

```

<figure><img src="../.gitbook/assets/image (3) (1).png" alt=""><figcaption></figcaption></figure>

{% hint style="danger" %}
元组中只有一个元素，逗号也不能省略！！！！
{% endhint %}



### ②元组访问与遍历

#### Ⅰ.for循环遍历



















元组支持我们的切片操作，并且还是用for循环遍历

```python
t = ('python', 'hello', 'world')

# 按照索引访问元组
print(t[0])

# 元组支持切片操作
t2 = t[0:3:2]
print(t2)

# 元组遍历
for item in t:
    print(item)

    
```

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

我们还可以用range＋len进行for遍历

```python
t = ('python', 'hello', 'world')

# 按照索引访问元组
print(t[0])

# 元组支持切片操作
t2 = t[0:3:2]
print(t2)

# 元组遍历
for item in range(len(t)):
    print(item, t[item])


```

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.enumerate()

我们之前说过枚举。

```python
t = ('python', 'hello', 'world')

# 按照索引访问元组
print(t[0])

# 元组支持切片操作
t2 = t[0:3:2]
print(t2)

# 元组遍历
for index, item in enumerate(t):
    print(index, item)


```

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

### ③元组生成式

元组生成式有一点区别。

我们先用生成器生成看看结果

```python
t1 = (i for i in range(1, 4))
print(t1)

```

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

我们可以看到这里并没有元组里面的元素，相反，这是生成器对象。

这就是我们说的区别，如果我们想要看到元组中的元素。那么我们可以将他转化为元组，再查看。

```python
t1 = (i for i in range(1, 4))
print(t1)

t1 = tuple(t1)
print(t1)


```

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

#### Ⅲ.\_\_next\_\_（）

这个\_\_next\_\_（）是针对生成器对象的遍历，也就是说，我们可以通过重复\_\_next\_\_（）去遍历生成器对象，让他把元组中的元素显示出来。

```python
t1 = (i for i in range(1, 4))
print(t1)

'''
t1 = tuple(t1)
print(t1)
'''

print(t1.__next__())
print(t1.__next__())
print(t1.__next__())




```

<figure><img src="../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
注意我们不能让他变成了元组之后再来使用这个，要在他是生成器对象时之后使用，不然就会失败。
{% endhint %}

这个\_\_next\_\_()是什么意思呢？他其实是取出生成器对象的意思。所以如果我们执行完我们如果让它变成元组的话，他会是个空元组。

<figure><img src="../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>





***

## （21）字典

<figure><img src="../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

### ①字典创建方法

<figure><img src="../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
我们需要提到一下，用zip函数创建后的得到的也是对象，并不是我们需要的字典，还需要通过dict（）函数才能真正创建dict（），可以验证一下。
{% endhint %}

```python
# 创建字典
d = {10: 'cat', 20: 'dog', 30: 'pet', 20:'zoo'}
print(d)

# 用zip函数创建
list1 = [10, 20, 30, 40]
list2 = ['cat', 'dog', 'pet', 'zoo', 'car']
d2 = zip(list1, list2)
print(d2)

# 用dic函数创建字典
d3 = dict(d2)
print(d3)
```

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

dict（）函数还能直接赋值。这里可以知道，在赋值的时候，=左边的是键，右边是值。并且是赋值，所以等号左边不能是常量，不然会报错。

```python
d1 = dict(cat=10, dog=20)
print(d1)

```

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>



②字典序列操作

因为字典属于序列，所以一些简单的查询的操作，对字典来说也是可以执行的。

```python
d1 = {10: 'cat', 20: 'dog', 30: 'rabbit', 40: 'pig'}


print('max:', max(d1))
print('min:', min(d1))
print('len:', len(d1))



```

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>



### ③字典的遍历

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

#### Ⅰ.d\[key]

这个取值方式如果key不存在，那么就会报错

```python
d = {'hello': 10, 'world': 20, 'python': 30}

# 取值
print(d['hello'])
print(d['java'])

print(d.get('java'))
print(d.get('java', '不存在'))

```

<figure><img src="../.gitbook/assets/image (255).png" alt=""><figcaption></figcaption></figure>

#### Ⅱ.d.get\[key]

这个取值方式如果哪个key不存在的话，我们可以指定他输出默认值。如果没有指定默认值就是None

```python
d = {'hello': 10, 'world': 20, 'python': 30}

# 取值
print(d.get('java'))
print(d.get('java', '不存在'))

```

<figure><img src="../.gitbook/assets/image (256).png" alt=""><figcaption></figcaption></figure>



#### Ⅲ.遍历

```python
d = {'hello': 10, 'world': 20, 'python': 30}

# 遍历
for item in d.items():
    print(item)

for key, value in d.items():
    print(key, value)
    

```

<figure><img src="../.gitbook/assets/image (257).png" alt=""><figcaption></figcaption></figure>



### ④字典操作

<figure><img src="../.gitbook/assets/image (258).png" alt=""><figcaption></figcaption></figure>

举个例子

```python
d = {1001: '李梅', 1002: '王华', 1003: '张锋'}
print(d)

# 向字典中添加元素
d[1004] = '张丽丽'
print(d)

# 获得key
keys = d.keys()
print(keys)

# 获取value
values = d.values()
print(values)
print(list(values))
print(tuple(values))

# 如果将字典中的元素转化为key-value形式，以元组方式进行展现
lst = list(d.items())
print(lst)

d = dict(lst)
print(d)

# 使用pop函数
print(d.pop(1001))
print(d)

# 随即删除
print(d.popitem())
print(d)

# 清空字典中的所有元素
d.clear()
print(d)


```

<figure><img src="../.gitbook/assets/image (259).png" alt=""><figcaption></figcaption></figure>

### ⑤字典生成式

<figure><img src="../.gitbook/assets/image (260).png" alt=""><figcaption></figcaption></figure>

```python
import random
d = {item: random.randint(1, 100) for item in range(4)}
print(d)

list1 = [1001, 1002, 1003]
list2 = ['Limei', 'Hanhe', 'WangYi']
d2 = {key: value for key,value in zip(list1, list2)}
print(d2)
```

<figure><img src="../.gitbook/assets/image (261).png" alt=""><figcaption></figcaption></figure>





***

## (22)集合

<figure><img src="../.gitbook/assets/image (262).png" alt=""><figcaption></figcaption></figure>

### ①集合创建













































































## 参考门：

{% embed url="https://www.bilibili.com/video/BV1wD4y1o7AS/?p=15&spm_id_from=pageDriver&vd_source=c5b5b4b3968ad0555ff989d461961de8" %}







