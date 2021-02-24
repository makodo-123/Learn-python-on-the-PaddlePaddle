# 课程地址https://aistudio.baidu.com/aistudio/course/introduce/7073

# Python笔记

## 数据类型

## 数字

#### 整数int

#### 浮点数float

```
round(num,dd)：对num保留dd位小数
```
#### 复数complex

#### 布尔型bool

```
True
False
```
#### None（布尔值为False）

## 强制类型转换

```
【int()】整数
提供了base参数，默认值为 10 ；如果传入base参数，就可以做N进制的
转换
【float()】浮点数
【complex()】创建一个复数
【str()】转换为字符串
【tuple()】将一个序列转换为一个元组
【list()】将一个序列转换为一个列表
【chr()】将一个整数转换为一个字符
【unichr】将整数转换为Unicode字符
【ord()】将字符转换为它的整数值
【hex()】将整数转换为十六进制字符串
【oct()】将整数转换为八进制字符串
```
## 字符串'str'

#### 索引【str[index]】

#### 切片【str[start:end:step]】（左闭右开）

#### 计数【str.count('str')】：不会交叉重复计数

#### 查找

```
【str.find('str1')】：返回从左第一个字符索引，找不到 返回-1 （不能用于列
表）
```

```
【str.index('str1')】：返回从左第一个字符索引，找不到 报错
```
#### 是否以...开头/结尾

```
my_string = 'hello_world'
【my_string.startswith('hello') 】# 是否以hello开始
【my_string.endswith('world') 】 # 是否以world结尾
返回布尔型
```
#### 拆分【str.split(sep,count)】：

```
以sep为分隔符进行分割，可包含多个字符，不含参数时即【' '】以空格分
隔，不能为空【''】
count指定分隔次数，默认为没有限制
返回一个数组
```
#### 替换【str.replace(old,new,[count])】：

```
count为最大替换量，从起始开始计数，默认替换所有
```
#### 插入【sep.join(seq)】

```
sep：分隔符可为空；seq：可迭代序列
```
#### 标准化/删除指定字符

```
【str.strip()】：删除 两边 的空格、换行符等；在括号内指定字符可删除指定
字符
【str.lstrip()】：删除 左 边空格、换行符等；在括号内指定字符可删除指定字
符
【str.rstrip()】：删除 右 边空格、换行符等；在括号内指定字符可删除指定字
符
```
#### 变形

```
【str.upper()】：小写变大写
【str.lower()】：大写变小写
【str.title()】：以标题形式将首字母大写
【str.capitalize()】：首字母大写
【str.casefold()】：所有字符小写
```
#### 格式化输出

```
【%】：例：print("姓名：%s,性别：%s年龄：%d" % (name,gender,age))
```

【.format】
不带编号即"{}"：例：print("姓名：{},性别：{}年龄：
{}".format(name,gender,age))
带数字编号可重复调用：=例：print("姓名：{0},性别：{1}年龄：{2}学生
姓名：{0}".format(name,gender,age))
带关键字，可重复，易懂：例：print("姓名：{name},性别：{gender}年
龄：{age}学生姓名：
{name}".format(name=name,gender=gender,age=age))
进阶（位于{}中的参数前）
【:<】左对齐
【:>】 右对齐
【:^】中间对齐
format数值
"c" 字符，在打印之前将整数转换成对应的unicode字符串
"b" 二进制
"d" 十进制数
"o" 八进制数
"x" 十六进制数
"e" 幂符号，用科学计数法打印数字，用"e"表示幂
"g" 一般格式，数字以fixed-point进行输出,当数值特别大的时候，用
幂形式打印
"n" 数字，当值为整数时和"d"相同，值为浮点数是和"g"相同，不同
的是他会根据区域设置插入数字分隔符。
"%" 百分数，数值乘以 100 打印，保留 6 位小数，值后面会有一个百
分号


##### "," 千位分隔符，货币表示或者大数据值经常用到

##### 更好的方法

```
print(f"大家好！我叫{name}，我的身高是{hight:.3f} cm, 数学成绩
{score_math}分,英语成绩{score_english}分")
```
### 列表list[]

### 索引，切片（同str）

### 添加新元素

```
末尾添加【list. append ()】：添加单项
指定位置添加【list. insert (2,'ooo')】若下标不存在则在末尾添加
```
### 合并列表

```
【list1.extend(list2)】：在list1里添加了list2的每个元素， list1变了 ， ist2没
变
【list1+list2】：生成了一个新列表， 原列表没变
```
### 计数【list.count(str,beg,end)】

### 查找【list.index(str,beg,end)】

### 翻转

```
【list.reverse()】反转列表， 无返回值 ，结果存在原列表中
```
```
【reversed(...)】对象可以是 列表和字符串 ，返回一个反转后的迭代器，但
必须要转化成list() ，不然不能使用
1
```

### 删除元素

```
弹出【list.pop(index)】
移除【list.remove()】
删除【del list[index]】
```
### 列表解析/列表生成式

```
【list=[表达式，for循环]】例：squares = [value**2 for value in range(1,11)]
可以筛选【list=[i for i in list_A if i in list_B]】
还可以【[m + n for m in 'ABC' for n in 'XYZ']】
```
### 生成器（generator）

```
不同于列表生成式：L = [x * x for x in range(10)]（用的是方括号）（不仅占
用很大的存储空间，如果我们仅仅需要访问前面几个元素，那后面绝大多数
元素占用的空间都白白浪费了）
生成器【g = (x * x for x in range(10))】（用的是圆括号）：用一个值，产生
一个值，用完就扔，只能用一次
【next（g）】：访问下一个，最后一个也迭代完了会报错
【yeild】
一个带有 yield 的函数就是一个 generator；函数每执行到一个 yield 语
句就会中断，并返回一个迭代值（类似于return），下次执行时从 yield
的下一个语句继续执行
使用 isgeneratorfunction 判断一个函数是否是一个特殊的 generator 函
数
```

```
CSDNhttps://blog.csdn.net/mieleizhi0522/article/details/82142856?ops
_request_misc=%25257B%252522request%25255Fid%252522%
3A%252522161260310016780265422235%252522%25252C%
2scm%252522%25253A%25252220140713.130102334..%252522%
5257D&request_id=161260310016780265422235&biz_id=0&utm_med
ium=distribute.pc_search_result.none-task-blog-2~all~top_click~defaul
t-1-82142856.first_rank_v2_pc_rank_v29&utm_term=yield
```
### 元组tuple()： 不可改

### 字典dict{key:value,......}： 里面是键值对，key不能重复

```
【.items()】以列表返回可遍历的(键, 值) 元组数组
【.keys()】以列表返回键【for name in favorite_languages.keys():】=【 for
name in favorite_languages: 】
【.values()】以列表返回值
【dic.clear()】清空字典
【dic.copy()】返回一个字典的浅复制
浅复制：改变复制后的对象会改变原对象；深复制：完全脱离原对象的复制
【dict.fromkeys(seq[, val])】创建一个新字典，以序列 seq 中元素做字典的键，
val 为字典所有键对应的初始值
【dic1.update(dict2)】把字典 2 更新进字典 1 中
例
```
```
【dic.get(key,提示信息)】=【dic.setdefault(key,提示信息)】通过字典的键查询
对应的值,如果没有找到,返回提示信息,默认返回None
例
```
```
字典创建三种方式有【{}】，内置函数【dict()】，内置函数【zip()】
【zip(x,y)】用于将可迭代对象x和y作为参数，将x和y中对应的元素打包成一个
元组，然后返回由这些元组组成的列表，元素个数与最短的列表一致
```

##### 例

```
【zip(*zip(x,y))】与 zip 相反，可理解为解压，返回二维矩阵式
例
```
```
【dict()】创建一个字典
字典生成式（类似于列表生成式）
例 1
```
```
例 2 【dict1={i+1:lst5[i] for i range(0,len(lst5)) }】
```
### 集合set{}： 里面是一堆key，同样不能重复

##### 集合生成式（类似于列表生成式）

## 语句

### 分支语句

```
if---elif---...else---
```
### 循环语句

```
for
遍历一个序列（字符串、列表）一个一个访问
【range（a,b）】：生成一个列表左闭右开
while
```

```
【continue】：跳过本轮继续下一轮
【break】：跳出本层循环
【pass】：什么都不做
```
## 函数

### 参数

#### 位置参数：按位置输入参数

#### 缺省参数：为参数设置默认值

##### 默认参数也可以传参，但默认参数要在位置参数后面，且后面不要再有参数

#### 可变参数

```
【*args】：表示任何多个无名参数，本质是tuple
```
#### 关键字参数

```
【**kwargs】表示关键字参数，本质是dict（传参时写成key=value）
```
#### 命名关键字参数

##### 【*,】后面的是命名关键字参数（即*占一个参数位）

#### 参数的组合

##### 参数定义的顺序：必选参数、默认参数、可变参数、命名关键字参数和关键

##### 字参数

##### 前面有可变参数时，省略命名关键字参数的【*,】

### 变量的作用域和global变量

##### 局部变量 作用域:在函数内

##### 全局变量 作用域:在函数外

##### 函数优先使用局部变量 在没有局部变量的情况下， 使用全局变量

```
函数外的变量在函数内使用后会变成局部变量，解决方法：使用global关键字
命名空间查找顺序： 局部命名空间→全局命名空间→内置命名空间
```
### return ...： 把后面的打包成tuple返回

### lambda 匿名函数

```
lambda 的主体是一个表达式，而不是一个代码块。仅仅能在 lambda 表达式中
封装有限的逻辑进去。
```

```
lambda 函数拥有自己的命名空间， 且不能访问自有参数列表之外或全局命名空
间里的参数 。
执行
方式 1
```
##### 方式 2

### 高阶函数： 一个函数接收另一个函数作为参数

##### 1

##### 2

##### 3

### map(function,iterable,...)函数

##### 第一个参数接受一个 函数名 ，后面的参数接受一个或多个可迭代的 序列 ，把函数

```
依次作用在list中的每一个元素上，得到一个新的list并返回。注意，map不改变
原list，而是返回一个新list
```

使用lambda匿名函数

通过lambda函数使返回值是一个元组

当不传入function时，map()就等同于zip()，将多个列表相同位置的元素归并到一
个元组

将其他转换为list
1

##### 2


```
提取字典中的key，并将结果放在一个list中
```
### reduce()

```
在运用前需要引入【 functools 】模块来调用
reduce有三个参数，第一个是函数function，第二个是序列sequence，第三个是
initial，为初始值，默认为None
用传给 reduce 中的函数 function（有两个参数）先对集合中的第 1 、 2 个元素进
行操作，得到的结果再与第三个数据用 function 函数运算，依此类推，最后得到
一个结果
```
##### 例


### sorted()

```
从小到大：【sorted([36, 5, -12, 9, -21])】
从大到小：【sorted([36, 5, -12, 9, -21], reverse=True )】
按绝对值从小到大：【sorted([36, 5, -12, 9, -21], key=abs)】
按某个值排序
```
### 迭代器/生成器

#### 迭代器

```
【iter(可迭代序列)】生成一个迭代器
【next()】
```
#### 生成器

### 其他一些函数

#### 【id()】：获取标识符

#### 【help()】：查看函数或模块用途的详细说明，相当于一个内置的

#### Python帮助手册


#### 【dir()】：不带参数时，可返回当前范围内的变量、方法和定义的

#### 类型列表；带参数时，可返回参数的属性、方法列表

### 装饰器

```
Python中一切皆对象，函数可以作为返回值返回，可以当做参数传递给一个函
数
闭包：
内部函数引用了外部函数中的变量形成闭包
闭包中被内部函数引用的变量， 不会因为外部函数结束而被释放掉 ，而是一
直存在内存中， 直到内部函数被调用结束
在函数外部无法拿到函数中的变量和内部函数，通常我们需要使用函数中的
变量或函数时，才去将变量或函数返回
例
```
```
【函数名.__closure__】判断是否是闭包，在函数是闭包函数时，返回一个
cell元素；不是闭包时，返回None
```
#### 装饰器 ：

```
https://blog.csdn.net/m0_51971452/article/details/111757163?ops_request
_misc=%25257B%252522request%25255Fid%252522%25253A%
1612920461 16780262571361%252522%25252C%252522scm%252522%
25253A%25252220140713.130102334..%252522%25257D&request_id=
612920461 16780262571361&biz_id=0&utm_medium=distribute.pc_search
_result.none-task-blog-2~all~top_click~default-1-111757163.first_rank_v2_
pc_rank_v29&utm_term=Python%25E8%25A3%2585%25E9%25A5%25B
0%25E5%2599%25A
就是给已有函数增加额外功能的函数，它本质上就是一个闭包函数
如果闭包函数的参数有且只有一个，并且是函数类型，那么这个闭包函
数称之为装饰器
例
```

##### 装饰器的语法糖写法：【@装饰器名】其后的函数会当做装饰器的参数

##### 传入装饰器，实际上扩展了其后的函数的功能

##### 例

##### 多个装饰器的使用

##### 多个装饰器的装饰过程：由内到外的一个装饰过程，先执行内部的

##### 装饰器，在执行外部的装饰器

##### 例


##### 带有参数的装饰器【@装饰器(参数,...)】

##### 使用带有参数的装饰器，其实是在装饰器外面又包裹了一个函数，

##### 使用该函数接收参数，返回是装饰器，因为 @ 符号需要配合装饰器

##### 实例使用

##### 例


##### 与类相关的

##### 用类实现装饰器

```
只要将某个类中多定义一个__call__方法，这样在类作为装饰器
装饰函数时，函数运行时就会运行__call__方法中的内容
```

##### 用装饰器修饰类

##### 类也可以看做是一个方法

### 偏函数

```
偏函数是functools模块中的一个方法,即functools.partial偏函数就是为了 固定某
些参数的传入 ,作为默认参数传入
```

## 类

### 定义一个类（三个部分）

##### 例

### 实例方法，类方法，静态方法

```
实例方法 ：定义时必须传入self作为第一个参数，可以访问实例变量，只能通过
实例名访问
类方法 【@classmethod】：定义时必须把类（cls）作为第一个参数传进去，可
以访问类变量，可以通过实例名或类名访问
静态变量 【@staticmethod】：不能访问类变量，也不能访问实例变量，可以通
过实例名或类名访问，就是普通的方法，但是和类紧密相关
```
### 私有属性，私有方法

```
在私有属性/私有方法前加'__'：私有属性【self.__name = a_name】，私有方法
【def __sanitize(self,time_string):】，均只能在内部访问，在外部不可访问
```
### 多态

##### 同一函数实现不同功能

### 类的继承

##### 例：


##### 多继承

## 文件

### 打开文件：

### 1.关键字with 在其后的代码结束后将文件关闭，open('path')打

### 开文件，read()返回一个字符串

### 2.逐行读取（文件中每行末尾都有一个换行符，print又会加上

### 一个换行符）（readlines() 从文件中读取每一行，并将其存储

### 在一个列表中）

##### 1

##### 2


## 异常处理

### try---except---else---finally---

#### 【 except Exception as e: 】Exception可以将所有的异常包括在

#### 内；将异常赋予变量e

### 断言assert expression： 与其让程序在晚些时候崩溃，不如在

### 错误条件出现时，就直接让程序崩溃

### raise： 自定义引发异常

### looging：

## 常见模块

### re模块 （正则表达式）

##### 正则表达式

##### 1


```
【re.compile(pattern,flags=0)】把一个字符串编译正则表达式，表示规则（字符
串的模式）
可选参数flags
【.match()】从头匹配
【.search()】返回找到的第一个
【.findall()】找到所有，返回一个列表
【.finditer()】找到所有，返回一个迭代器
【.group()】
【.groups()】返回一个tuple
【.start()】返回匹配到字符串的起始位置
【.end()】返回匹配到字符串的结束位置
【.span()】返回一个二元tuple表示范围（start，end）
【str.sub(repl,string,count)】用repl替换string中的str，返回替换后的字符串，若
找不到返回原字符串，count为最大替换次数，不指定是替换全部
【re.sub(pattern,repl,string,count,flag)】
```
### os模块

```
【os.name】给出操作系统的名字（Windows：'nt'，Linux：'posix'）
【os.getcwd()】查看当前所在路径
【os.walk】遍历一个目录内各个子目录和子文件，返回 三元tuple
【os.walk(top, topdown=True, οnerrοr=None, followlinks=False) 】可以得
到一系列 三元tupple 每个tuple都是(dirpath, dirnames, filenames)
第一个为起始路径，第二个为起始路径下的文件夹，第三个是起始路径下的
文件
```

```
dirpath 是一个string，代表 目录 的路径
dirnames 是一个list，包含了dirpath下所有 子目录 的名字
filenames 是一个list，包含了非目录 文件 的名字
例
```
【os.listdir(path)】列举目录下的所有文件，返回 **列表** 类型
【os.rename('oldname','newname')】文件重命名
【os.mknod(filename)】创建文件
【os.remove(filename)】删除指定文件
【os.mkdir(path)】，创建指定目录，只能创建一层
【os.makedirs(path)】递归创建目录
【os.rmdir(path)】删除目录（不能递归删，只能一层层删）
【os.removedirs(path)】递归删除空目录，非空目录不能删
【os.chdir(path)】更改目录
【os.path.abspath(path)】返回path的绝对路径
【os.path.split(path)】将路径分解为（文件夹，文件名），返回元组类型
【os.path.splitext(filename)】分离文件名和后缀名


```
【os.path.join(path1,path2,......)】将path进行组合，若有绝对路径，则之前的
path将被删除
sep.join(seq)： 连接字符串数组。将字符串、元组、列表中的元素以指定的
字符(分隔符)连接生成一个新的字符串；os.path.join()： 将多个路径组合后
返回
如果各组件名首字母不包含’/’，则函数会自动加上
例
```
##### 如果有一个组件是一个绝对路径，则在它之前的所有组件均会被舍弃

##### 如果最后一个组件为空，则生成的路径以一个’/’分隔符结尾

##### 注意：若出现”./”开头的参数，会从”./”开头的参数的上一个参数开始拼接

```
【os.path.dirname(path)】返回path中文件夹部分，
【os.path.basename(path)】返回path中文件名
【os.path.getmtime(path)】文件最后修改时间
【os.path.getatime(path)】文件最后访问时间
【os.path.getctime(path)】文件创建时间
【os.path.getsize(path)】查看文件大小，若是文件夹返回 0
【os.path.isfile(filename)】判断对象是否为文件，返回布尔型
【os.path.isdir(path)】判断对象是否为目录，返回布尔型
【os.path.exists(path)】判断文件/文件夹是否存在，返回布尔型
```
### sys模块


### request模块

```
http://cn.python-requests.org/zh_CN/latest/
```
### BeautifulSoup库

```
https://beautifulsoup.readthedocs.io/zh_CN/v4.4.0/
```
### Numpy库 （N维数组对象和向量运算）

### https://www.numpy.org.cn/

### 主要对象是同种元素的多维数组，这是一个所有的元素都是

### 一种类型、通过一个正整数元组索引的元素表格(通常是元素

### 是数字)， 维度(dimensions) 叫做 轴(axes) ，轴的个数叫做 秩

### (rank)

### import numpy as np

### 数组的信息

```
ndarray.ndim - 数组的轴（维度）的个数
ndarray.shape - 数组的维度
这是一个整数的元组，表示每个维度中数组的大小。对于有 n 行和 m 列
的矩阵，shape 将是 (n,m)。因此，shape 元组的长度就是rank或维度的
个数 ndim。
ndarray.size - 数组元素的总数
ndarray.dtype - 一个描述数组中元素类型的对象
可以使用标准的Python类型创建或指定dtype。另外NumPy提供它自己
的类型。例如numpy.int32、numpy.int16和numpy.float64
ndarray.itemsize - 数组中每个元素的字节大小
```
### 数组的创建

```
【np.array()】接受序列型对象产生一个新的numpy数组（嵌套序列，比如
由一组等长列表组成的列表，将会被转换为一个多维数组）
1
```
##### 2.数组类型可以在创建时显示指定


##### 3.有些操作符像【+=】和【*=】被用来更改已存在数组而不创建一个新

##### 的数组

```
【np.zeros()】可以创建指定长度或者形状的全 0 数组
【np.ones()】可以创建指定长度或者形状的全 1 数组
【np.empty()】创建一个数组，其初始内容是随机的，取决于内存的状态
【np.range()】类似于range，返回的是数组
输出数组信息
数组维度【print(array.ndim)】
数组形状【print(array.shape)】
数组元素个数【print(array.size)】
数组元素类型【print(array.dtype)】
```
#### 改变形状

```
【np.reshape()】重新定义数字的形状（可以多维）
```
```
【.flat()】是一个数组元素迭代器
【np.flatten()】返回一份数组拷贝，对拷贝所做的修改不会影响原始数组
【np.resize()】返回指定形状的新数组,如果新数组大小大于原始大小，则包
含原始数组中的元素的副本
```

```
【np.ravel()】返回展开数组，返回的是数组视图
【np.append()】将值添加到数组末尾
【np.insert(arr, index, values, axis)】沿指定轴将值插入到指定下标之前
【np.delete(arr, index, axis)】删掉某个轴的子数组，并返回删除后的新数组
【np.unique(arr, return_index, return_inverse, return_counts)】查找数组内
的唯一元素
arr：输入数组，如果不是一维数组则会展开
return_index：如果为true，返回新列表元素在旧列表中的位置（下
标），并以列表形式储
return_inverse：如果为true，返回旧列表元素在新列表中的位置（下
标），并以列表形式储
return_counts：如果为true，返回去重数组中的元素在原数组中的出现
次数
翻转数组
【np.transpose()】=【array1.T】转置
【np.rollaxis(arr, axis, start)】向后滚动特定的轴到一个特定位置
arr：数组
axis：要向后滚动的轴，其它轴的相对位置不会改变
start：默认为零，表示完整的滚动。会滚动到特定位置。
【np.swapaxes(arr, axis1, axis2)】交换数组的两个轴
arr：输入的数组
axis1：对应第一个轴的整数
axis2：对应第二个轴的整数
改变维度
【np.broadcast(x,y)】产生模仿广播的对象，对 y 广播 x
【np.broadcast_to(a,(4,4))】将数组a广播到新形状(4,4)
【np.expand_dims(arr, axis)】通过在指定位置插入新的轴来扩展数组的
形状
【np.squeeze(arr, axis)】从数组的形状中删除一维条目
```
#### 组合和分割

##### 组合 不同的数组

```
【np.concatenate((a1, a2, ...), axis)】连接沿现有轴的数组序列
a1, a2, ...：相同类型的数组
axis：沿着它连接数组的轴，默认为 0
【np.stack(arrays, axis)】沿着新的轴加入一系列数组
arrays相同形状的数组序列
axis：返回数组中的轴，输入数组沿着它来堆叠
```

```
沿不同轴将数组堆叠：【column_stack((a,b))】=【vstack((a,b))】；
【row_stack((a,b))】=【hstack((a,b))】；
```
```
r_[]和c_[]对创建沿着一个方向组合的数很有用，它们允许范围符号(“:”):
```
```
将一个数组 分割 (split)成几个小数组
【hsplit()】将数组沿水平轴分割
```
```
【vsplit()】沿着纵向的轴分割
```
#### 数组的计算

##### 矩阵的基础运算

##### 例


##### 矩阵乘法

##### 例

通用函数：NumPy提供常见的数学函数如sin,cos和exp
其他
1 ，最值


##### 2 ，转置和拍平

##### 3 ，运算的是不同类型的数组时

#### 数组的索引与切片

##### 例


#### 复制和视图

##### 完全不复制：简单的赋值不拷贝数组对象或它们的数据

##### 1

```
视图(view)和浅复制
1
```

##### 切片数组返回它的一个视图

##### 1

##### 深复制

##### 1

#### 广播法则

##### 广播法则能使通用函数有意义地处理不具有相同形状的输入

##### 广播第一法则是，如果所有的输入数组维度不都相同，一个“1”将被重复地添

##### 加在维度较小的数组上直至所有的数组拥有一样的维度

##### 广播第二法则确定长度为 1 的数组沿着特殊的方向表现地好像它有沿着那个

##### 方向最大形状的大小。对数组来说，沿着那个维度的数组元素的值理应相同

#### 花哨的索引和索引技巧

##### 通过数组索引

##### 通过布尔数组索引

```
ix_()函数
用字符串索引
```
#### 线性代数

### Pandas库 （Numpy的升级版）

```
https://www.pypandas.cn/ （基于numpy，numpy的升级版本）
import pandas as pd import numpy as np
【Series】带标签的一维同构数组
```

是一种类似于一维数组的对象，它由一维数组（各种numpy数据类型）以及
一组与之相关的数据标签（即索引）组成，可理解为带标签的一维数组

使用index设置索引列表（与字典不同的是，Seris允许索引重复）

Series 可以用字典实例化

通过Series的values和index属性获取其数组表示形式和索引对象
1


##### 2


##### 算术运算中自动对齐不同索引的数据


【DataFrame】带标签的，大小可变的，二维异构表格
DataFrame是一个表格型的数据结构，类似于Excel或sql表，它含有一组有
序的列，每列可以是不同的值类型（数值、字符串、布尔值等），既有行索
引也有列索引，它可以被看做由Series组成的字典（共用同一个索引）

```
如果指定了列顺序，则DataFrame的列就会按照指定顺序进行排列
```
```
跟原Series一样，如果传入的列在数据中找不到，就会产生NAN值
```
```
用 Series 字典或字典生成 DataFrame
```

```
通过类似字典标记的方式或属性的方式，可以将DataFrame的列获取为一个
Series，返回的Series拥有原DataFrame相同的索引
```
```
列可以通过赋值的方式进行修改,例如，给那个空的“delt”列赋上一个标量值
或一组值
```
### Matplotlib库 （绘图，可视化）

```
https://www.matplotlib.org.cn/
matplotlib.pylot是绘制各类可视化图形的命令字库
安装【!pip install matplotlib】
```

### PIL库 （图像处理）

```
安装pillow【!pip install pillow】
展示图片，并获取图像的模式，长，宽
```

##### 图片旋转


##### 镜像效果：左右旋转、上下旋转

##### 图片剪切

```
剪切 crop()四个参数分别是：(左上角点的x坐标，左上角点的y坐标，右下角
点的x坐标，右下角点的y坐标)
```
##### 图片缩放


### 飞桨PaddlePaddle

```
https://www.paddlepaddle.org.cn/documentation/docs/zh/guides/index_cn.html
```

