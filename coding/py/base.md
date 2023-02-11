# 基础语法
## 格式
### 脚本说明

#### 解释器
```python
#!/usr/bin/python
#!/usr/bin/env python
```
编写 python 脚本时, 需要在第一行说明采用的解释器
1. 写法1 表示采用默认的解释器
2. 写法2 表示在环境变量中查找使用的解释器, 推荐

#### 脚本编码
```python
# -*- coding: UTF-8 -*-
```
编写 python 脚本时, 需要在第二行有此语句表明编码

### 标识符
1. 单下划线开头 _foo 的代表不能直接访问的类属性, 不能用 from xxx import * 而导入
2. 以双下划线开头的 __foo 代表类的私有成员
3. 以双下划线开头和结尾的 __foo__ 代表 Python 里特殊方法专用的标识

### 行和缩进
python 最具特色的就是用缩进来写模块, 缩进可以是 单个制表符 或 两个空格 或 四个空格, 但需要统一

### 多行语句
1. 可以使用斜杠 (\\) 将一行的语句分为多行显示
2. 语句中包含 [], {} 或 () 括号就不需要使用多行连接符

### 引号
1. Python 可以使用引号( ' ), 双引号( " ), 三引号( ''' 或 """ ) 表示字符串
2. 三引号可以由多行组成, 编写多行文本的快捷语法

### 注释
1. python中单行注释采用 # 开头
2. python 中多行注释使用三个单引号 ''' 或三个双引号 """
eg.
```python
'''
这是多行注释，使用单引号。
这是多行注释，使用单引号。
'''

"""
这是多行注释，使用双引号。
这是多行注释，使用双引号。
"""
```

### 同一行显示多条语句
Python可以在同一行中使用多条语句，语句之间使用分号(;)分割

## 变量
### 标准数据类型
* Numbers (数字)
    * int (有符号整型)
    * float (浮点型)
    * complex (复数) 使用 1j 表示虚数单位
    * bool (布尔)
* String (字符串)
* List (列表)
* Tuple (元组)
* Dictionary (字典)
* Set (集合)
* None (无类型)

#### 删除变量
del [变量]
删除指定变量

#### 类型转换
与 C 类似, 具体查表

## 运算符
仅列出与 C 的不同
|操作符|功能|
|--|--|--|
|**|幂运算|
|//|整除(向下取整)|
|~|按位取反|
|and|逻辑与|
|or|逻辑或|
|not|逻辑非|
|is|判断变量地址是否相同|
|in|判断元素是否在列表/字符串中|

* 存在运算赋值 (+= 等)
* 不存在自增/自减运算符
* 逻辑运算使用 and, or, not, 同样有短路求值
* 位运算不变

## 流程控制
* 没有 switch/case 语句

### 条件语句
```python
if 判断条件1:
    执行语句1……
elif 判断条件2:
    执行语句2……
elif 判断条件3:
    执行语句3……
else:
    执行语句4……
```
注意条件后的冒号 :

### while 循环
```python
while 判断条件：
    执行语句……
```

### for 循环
```python
for ([迭代索引],) [迭代变量] in 迭代体:
   执行语句
```
可通过 range() 生成线性迭代体

### 循环控制
1. break 打破一层循环
2. continue 进入下一轮循环
3. pass 不进行任何操作

## 字符串
### 字符串索引
1. 从左往右索引时, 索引值由 0 开始
2. 从右往左索引时, 索引值由 -1 开始

### 截取字符串
1. 使用语法 [头下标(包含):尾下标(不包含)], 可用于截取子字符串
2. 省略下标则表示从最左端/右端选择

### 字符串运算符
|操作符|功能|示例|
|--|--|--|
|+|连接字符串|
|*|重复输出字符串|
|in|判断元素是否在字符串中|"Hello" in "ell" = true|
|not in|判断元素是否不在字符串中|

### 转义与格式化
1. 格式化转义符与 C 相同
2. 格式化语法 [格式化字符串] % (格式化参数)

### 字符串标记
放在字符串最前处, eg R"Hello"
1. r/R 原始字符串, 不转义
2. u unicode 字符串

## 列表
即数组, 但可以包含不同类型的元素

### 添加元素
list.append([元素])
向列表后方添加元素

### 删除元素
del list[n]
删除第 n 个元素

### 索引
同字符串, 也可使用索引截取子列表

### 深拷贝
列表的赋值与传递为浅拷贝, 可通过赋值子列表的方式深拷贝
```python
copy_list = original_list[:]
```

### 元组
1. 与列表相同, 但元组不能修改与删除, 可以复制与连接
2. 使用 () 创建与表示

## 字典
### 创建字典
```python
var1 = {[键1]:[值1], [键2]:[值2], ...}
```
* 键与值可以是任意类型, 但键的值不能改变

### 修改字典
1. 使用 [键] 索引字典
2. 当使用一个不存在的键时, 将自动创建
3. 使用 del dict[key] 删除键值对

## 集合
无序不重复的元素序列
### 创建集合
```python
set1 = set([元素1], [元素2], ...)
```
### 修改集合
#### 添加元素
1. set.add(x)
添加元素, 如果元素已存在则不操作
2. set.update(x)
添加列表, 元组内的元素

#### 删除元素
1. set.discard(x)
删除元素, 如果元素不存在不会出错
2. set.remove(x)
删除元素, 如果元素不存在会出错

#### 集合大小
len(set)

#### 元素是否在集合中
x in set
判断 x 是否在集合中

## 函数
```python
def 函数名(函数参数):
   "函数_文档字符串"
   函数体
   return [返回值]
```

1. return [表达式] 结束函数
2. 不带表达式的return相当于返回 None
3. 函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明
4. 函数文档字符串用三引号可实现多行

### 参数传递
#### 可变类型
类似 C++ 的引用传递
列表, 字典使用此方式传递参数
* 赋值中, 此两种类型为浅拷贝

#### 不可变类型
类似 C++ 的值传递
整数, 字符串, 元组使用此方式传递参数
* 赋值中, 此类类型为深拷贝

### 参数类型
#### 关键字传参
可以指定参变量的方式传参
eg. fun(a = 10, b = 20)

#### 默认参数
可以在函数参数中指定默认参数

#### 不定长参数
加了星号 (*) 的变量名会存放所有未命名的变量参数
eg. def fun(a, b, *var_tuple)
其中 var_tuple 为元组

#### 不定长带名称参数
加了双星号 (**) 的变量名将会存放所有由命名但没有定义的变量参数
eg. def save(file, *args, **kwd)
其中, kwd 为字典, 调用 save(xxx = val) 时, 产生键值对 kwd['xxx'] = val 

### 匿名函数
```python
lambda [参数1], [参数2], ... : 函数体
```
lambda函数拥有自己的命名空间, 且不能访问自有参数列表之外或全局命名空间里的参数

### 作用域
1. 函数内的局部变量无法被外部访问
2. 函数要访问外部的全局变量, 需要使用 global [全局变量] 声明

### 传递函数
1. 函数可以作为参数传递
2. 函数可在函数体内定义, 然后作为返回值返回
eg. 
```python
def funx(x):
    def funy(y):
        return x * y
    return funy

funx(7)(8)
```

### 返回值
函数可以返回多个值, 使用 return a1, a2, ... 表示
返回值将以元组的形式返回, 或者可用多个变量接收返回值
eg.
```python
def fun() :
    return 1, 2, 3

a, b, c = fun()
print(a, b, c)
```
将输出 1 2 3

## 模块
### 模块导入
```python
import [模块1], [模块2], ...
```
调用此法导入的模块时, 需要使用 [模块名].[模块方法] 的方式使用

### 全局导入
```python
from [模块] import [模块方法/*]
```
导入模块方法, 使用 * 则是导入全部方法, 用此法导入的方法将作为全局方法

### 别名导入
```python
import [模块] as [别名] 
```
可以对导入的模块起别名

### 模块相关函数
1. dir([模块])
查找模块中所有的函数, 变量
2. globals()
查找所有全局变量
3. locals()
查找所有局部变量

### 包
1. 一个包中可以包含多个模块
2. 包为一个文件夹, 里面有多个子模块(.py)
3. 包中必须有文件 \_\_init\_\_.py, 用于在启动包时调用

### \_\_name\_\_ 属性
模块第一次被另一个程序引用时, 将运行模块内的程序, 通过 \_\_name\_\_ 属性, 判断模块是被引用还是作为独立的程序运行
```python
if __name__ == '__main__':
   [程序自身在运行]
else:
   [作为模块运行]
```
每个模块都有一个 \_\_name\_\_ 属性, 当其值是 '\_\_main\_\_' 时, 表明该模块自身在运行, 否则是被引入

### dir() 函数
dir([模块导入名])
可以找到模块内定义的所有名称, 以一个字符串列表的形式返回

### 常用模块
|模块名|功能|
|--|--|
|math|数学库|
|cmath|复数运算|
|time|时间库|
|calendar|日历库|
|sys|系统信息|
|os|管理系统/文件|
|re|正则表达式|
|json|json 解析|

# 常用模块
## 输入输出
### 打印到屏幕
print([表达式1], [表达式2], ...)
将表达式转为字符串, 打印到屏幕上

### 获取输入
1. raw_input([输入提示])
从屏幕上获取一行, 返回字符串
2. input([输入提示])
从屏幕上获取一行, 作为 python 表达式解析, 然后返回
3. 如果要读取数字等, 需要使用类型转换
```python
a = int(input("..."))
```

### 推导式
通过字符串, 从一个数据序列构建另一个序列, 可以被 input 函数解析或直接使用表示变量的值

#### 列表推导式
```python
res = [out_exp_res for out_exp in input_list if condition]
```
1. res 结果列表
2. out_exp_res 遍历列表元素的表达式, 返回值作为列表元素
3. out_exp 表达式中的迭代变量
4. input_list 输入列表(可迭代类型)
5. condition 迭代变量满足条件

* eg. 过滤掉长度小于或等于 3 的字符串列表, 并将剩下的转换成大写字母
```python
* new_names = [it.upper() for it in names if len(it) > 3]
```

* 注意, 输入列表也可以是返回列表的函数, 如 range()

#### 字典推导式
```python
res = { key_expr: value_expr for value in collection if condition }
```
1. res 结果字典
2. key_expr 遍历列表元素的表达式, 返回值作为键名
3. value_expr 遍历列表元素的表达式, 返回值作为键值
4. value 表达式中的迭代变量
5. collection 输入列表(可迭代类型)
6. condition 迭代变量满足条件

* eg. 使用字符串及其长度创建字典
```python
newdict = {key:len(key) for key in listdemo}
```

#### 集合推导式
```python
res = { expression for item in Sequence if conditional }
```
与列表相同, 使用 {} 包裹

#### 元组推导式
```python
res = (expression for item in Sequence if conditional )
```
与列表相同, 使用 () 包裹
注意元组推导式返回的是生成器对象, 不是元组
生成器对象不直接保存数据, 而是在迭代时计算结果
需要使用以下方法生成元组
```python
res = tuple([生成器])
```

#### 分支推导式
```python
res = [结果1 if 判断条件 else 结果2 for 变量名 in 原列表]
```

## 文件操作
### 打开文件
```python
file a = open(file, mode = 'r', encoding = 'utf8')
```
* file
文件路径
* mode
文件打开模式

### 文件方法
使用 open 函数后, 将创建 file 对象, 通过其成员函数操作文件
1. file.close
关闭文件
2. file.read([size])
读取字符, 如果负数则读取所有
3. file.readline()
读取整行, 包括 \n
4. file.seek([偏移])
设置当前位置
5. file.tell()
获取当前位置
6. file.write([字符串])
向文件中写入字符串

## 常用操作
### 操作系统接口
使用模块 os
1. os.getcwd()
获取当前工作目录
2. os.chdir([路径])
切换工作目录
3. os.remove([路径])
删除文件
4. os.rename([旧名称], [新名称])
重命名文件或目录
5. os.system()
执行系统命令
6. os.access([路径], [操作])
检验是否有权限操作文件
7. os.path
与路径, 文件信息有关的子模块
* 对于操作文件夹, 可能需要具有递归版本的函数, 查表

### 文件搜索
使用模块 glob
1. glob.glob([带有通配符的路径])
返回符合通配符的路径

### 系统交互接口
使用模块 sys
1. sys.argv
获取命令行参数
2. sys.stdin/stdout/stderr.write/read()
重定向输入输出流
3. sys.exit()
终止脚本

### 正则表达式
1. r"[正则表达式]"
定义正则表达式
2. re.findall([正则表达式], [字符串])
正则表达式匹配

# 面向对象
## 创建类
### 类的基本结构
```python
class [类名]:
    "[类说明文档]"
    [类体]
```

### 成员函数
类的成员函数与一般函数相同, 均使用 def 定义, 但成员函数的第一个参数必定是向类本身的实例(类似 this), 通常命名为 self

### 构造函数
类的构造函数使用名称 \_\_init\_\_(self, [参数1], [参数2], ...)
通常在类的构造函数中为成员赋值, eg
```python
class test:
    "测试类"
    def __init__(self, arg1):
        self.arg1 = arg1
        return
```

### 类的使用
与 C++ 基本类似

### 类的特殊属性
1. \_\_dict\_\_ : 类的属性（包含一个字典，由类的数据属性组成）
2. \_\_doc\_\_ :类的文档字符串
3. \_\_name\_\_: 类名
4. \_\_module\_\_: 类定义所在的模块（类的全名是'\_\_main\_\_.className'，如果类位于一个导入模块mymod中，那么className.\_\_module\_\_ 等于 mymod）
5. \_\_bases\_\_ : 类的所有父类构成元素（包含了一个由所有父类组成的元组）

### 类的构析
类采用引用计数, 当类不再被任何位置引用时, 将自动构析类
```python
a = test_class()
b = a
c[0] = a

del a
b = 100
c[0] = 100
# 此时实例不再被引用, 将被构析
```
类在构析时, 将调用构析函数  \_\_del\_\_()

### 类的继承
```python
class 派生类名(基类名1, 基类名2, ...)
    ...
```

#### 继承类的构造函数
派生类将不会再调用父类的构造函数, 如果要调用父类成员, 需要使用语法
```python
class Child(Father):
    def __init__(self):
        Father.__init__(self)
```

#### 成员重用
与父类同名的方法将自动覆盖
使用 [父类名].[父类成员](self, 参数...)
调用父类的成员

### 类的运算符重载
1. 字符串转化
\_\_str\_\_(self)
2. 对象比较
\_\_cmp\_\_(self, x)
3. 加法重载(其他重载查表)
\_\_add\_\_(self, x)
4. 解释器读取
\_\_repr\_\_(self, x)

### 私有成员
当成员名称为 __[成员名] 时, 认为是私有成员

## 迭代器与生成器
### 迭代器
#### 创建迭代器
```python
it = iter(list1)
```
通过 iter 函数创建迭代器, iter 的参数可以是任何可迭代类型

#### 遍历迭代器
```python
x = next(it)
```
* 对迭代器使用 next, 实现遍历迭代器
* 当迭代器遍历结束, 将产生异常, 可使用 try 捕捉异常

#### 迭代器类型
当一个类具有成员函数 \_\_iter\_\_ 与 \_\_next\_\_, 则可以作为迭代器使用
1. \_\_iter\_\_
使用 iter 时调用此成员, 返回一个具有 \_\_next\_\_ 的对象, 通常是 self
2. \_\_next\_\_
使用 next 时调用此成员, 返回迭代器指向的值, 并使迭代器向下移动

#### StopIteration 异常
当迭代器遍历完所有元素时, 需要在 \_\_next\_\_ 中抛出此异常, 让迭代终止
```python
def __next__(self):
    if it > 10:
        raise StopIteration
    else
        it += 1
        return it
```

#### 遍历迭代器
使用 for 循环遍历迭代器
```python
for x in sequence:
    print(x)
```
相当于先调用 iter 获取迭代器, 然后每次循环将 next 的结果赋给 x, 直到产生 StopIteration 异常

### 生成器
* 使用了 yield 的函数被称为生成器
* 每次遇到 yield 时函数会暂停并保存当前所有的运行信息, 返回 yield 的值, 并在下一次执行 next() 方法时从当前位置继续运行
* 基本结构
```python
def generator(n): # 生成器函数
    counter = 0 # 利用 counter 记录当前迭代次数
    while True:
        if (counter >= n): # 利用 n 记录总计迭代次数
            return # 当运行到 return 时, 抛出 StopIteration 异常
        [迭代计算]
        yield [迭代结果]
        counter += 1

for it in generator(10): # 此时 f 为一个迭代十次的迭代器
    [遍历] 
```

## 异常
### 异常类型
[Python 标准异常](https://www.runoob.com/python/python-exceptions.html)
Python 异常基类 Exception

### 基本异常处理
```python
try:  
    [正常执行模块]  
except [异常 A]:  
    [发生A错误时执行]  
except [异常 B] as e(异常对象名):  
    [发生B错误时执行]
    print(e) # 打印异常信息
except:  
    [发生任何其他错误时执行] 
else:  
    [没有错误时执行]  
finally:  
    [总是执行]  
```

### 抛出异常
```python
raise [异常类型]([异常信息])
```
抛出异常后, 后方的代码不会再执行

### 简单异常处理
对于存在成员函数 \_\_exit\_\_() 与 \_\_enter\_\_() 的类, 可以简化异常处理过程

```python
with [入口表达式] as val(变量):
    [处理语句]
```

等价于

```python
try:
    tmp = [入口表达式]
    val = tmp.__enter__()
    [处理语句]
finally:
    tmp.__exit__()
```

此时, 无论发生什么异常, 都能保证 tmp.\_\_exit\_\_() 执行, 使 [入口表达式] 产生的类正常释放
通常将此方法用于文件输入输出, 保证文件能正常关闭

```python
text = ""
with open("test.txt", "r") as file:
    text = file.read()
```
