

# Python基础语法

### 运算符

> is 与 == 区别：
> is 用于判断两个变量引用对象是否为同一个(同一块内存空间)， == 用于判断引用变量的值是否相等。

```python
>>> a = [1, 2, 3]
>>> b = a
>>> b is a 
True
>>> b == a
True
>>> b = a[:]
>>> b is a
False
>>> b == a
True
```

| 运算符                   | 描述                                                   |
| :----------------------- | :----------------------------------------------------- |
| ==**==                   | ==指数 (最高优先级)==                                  |
| ~ + -                    | 按位翻转, 一元加号和减号 (最后两个的方法名为 +@ 和 -@) |
| * / % ==//==             | 乘，除，取模和==取整除==                               |
| + -                      | 加法减法                                               |
| >> <<                    | 右移，左移运算符                                       |
| &                        | 位 ‘AND’                                               |
| ^ \|                     | 位运算符                                               |
| <= < > >=                | 比较运算符                                             |
| <> == !=                 | 等于运算符                                             |
| = %= /= //= -= += *= **= | 赋值运算符                                             |
| is is not                | 身份运算符                                             |
| in not in                | 成员运算符                                             |
| not and or               | 逻辑运算符                                             |

### 数据类型

Python基本数据类型一般分为6种：数值（Numbers）、字符串（String）、列表（List）、元组（Tuple）、字典（Dictionary）、集合（Set）。

- Python 中的变量赋值不需要类型声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

Python允许你同时为多个变量赋值。例如：

```
a = b = c = 1
```

以上实例，创建一个整型对象，值为1，三个变量被分配到相同的内存空间上。

您也可以为多个对象指定多个变量。例如：

```
a, b, c = 1, 2, "ShowMeAI"
```

以上实例，两个整型对象 1 和 2 分别分配给变量 a 和 b，字符串对象 “ShowMeAI” 分配给变量 c。

1. 数值：`int, float, bool, complex(复数)`

   ```python
   del num_a,num_b # 删除 
   ```

2. 字符串

   字符串取值顺序：

   - 从左到右索引默认0开始的，最大范围是字符串长度少1
   - 从右到左索引默认-1开始的，最大范围是字符串开头

从字符串中获取一段子字符串的话，可以使用 **[头下标:尾下标]** 来截取相应的字符串，其中下标是从 0 开始算起，可以是正数或负数，下标可以为空表示取到头或尾。

**[头下标:尾下标]** 获取的子字符串包含头下标的字符，但==不包含尾下标的字符==。

```py
str = 'Hello ShowMeAI!'

print(str) # 输出完整字符串

print(str[0]) # 输出字符串中的第一个字符

print(str[2:5]) # 输出字符串中第三个至第六个之间的字符串

print(str[2:]) # 输出从第三个字符开始的字符串

print(str * 2) # 输出字符串两次

print(str + " Awesome") # 输出连接的字符串
```

以上实例输出结果：

```python
Hello ShowMeAI!
H
llo
llo ShowMeAI!
Hello ShowMeAI!Hello ShowMeAI!
Hello ShowMeAI! Awesome
```

```python
>>>letters = ['s','h','o','w','m','e']
>>>letters = [1:4:2]

['h','w']
```

3. 列表

   List（列表） 是 Python 中使用最频繁的数据类型。

   加号 **+** 是列表连接运算符，星号 ***** 是重复操作。

   ```python
   list = [ 'ShowMeAI', 786 , 2.23, 'show', 70.2 ]
   tinylist = [123, 'show']
   print(list) # 输出完整列表
   print(list[0]) # 输出列表的第一个元素
   print(list[1:3]) # 输出第二个至第三个元素 
   print(list[2:]) # 输出从第三个开始至列表末尾的所有元素
   print(tinylist * 2) # 输出列表两次
   print(list + tinylist) # 打印组合的列表1
   ```

   以上实例输出结果：

   ```python
   ['ShowMeAI', 786, 2.23, 'show', 70.2]
   ShowMeAI[786, 2.23]
   [2.23, 'show', 70.2]
   [123, 'show', 123, 'show']
   ['ShowMeAI', 786, 2.23, 'show', 70.2, 123, 'show']
   ```

4. 元组

   元组用 **()** 标识。内部元素用逗号隔开。但是元组不能二次赋值，相当于只读列表。

   以下是元组无效的，因为元组是不允许更新的。而列表是允许更新的：

   ```python
   tuple = ( 'ShowMeAI', 345 , 2.23, 'show', 456.2 )
   list = [ 'ShowMeAI', 345 , 2.23, 'show', 456.2 ]
   tuple[2] = 100    # 元组中是非法应用
   list[2] = 100     # 列表中是合法应用
   ```

5. 字典

   字典(dictionary)是除列表以外python之中最灵活的内置数据结构类型。列表是有序的对象集合，字典是无序的对象集合。

   两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。

   字典用”{ }”标识。字典由索引(key)和它对应的值value组成。

   ```python
   >>>d = {key1 : value1, key2 : value2, key3 : value3}
   ```

   ```python
   dict = {}
   dict['one'] = "This is one"
   dict[2] = "This is two"
   tinydict = {'name': 'ShowMeAI','code':3456, 'dept': 'AI'}
   print(dict['one']) # 输出键为'one' 的值
   print(dict[2]) # 输出键为 2 的值
   print(tinydict) # 输出完整的字典
   print(tinydict.keys()) # 输出所有键
   print(tinydict.values()) # 输出所有值
   ```

   输出结果为：

   ```python
   This is one
   This is two
   {'name': 'ShowMeAI', 'code': 3456, 'dept': 'AI'}
   dict_keys(['name', 'code', 'dept'])
   dict_values(['ShowMeAI', 3456, 'AI'])
   ```

另外一种执行循环的遍历方式是通过索引

```
fruits = ['香蕉', '苹果',  '葡萄']
for index in range(len(fruits)):
	print('当前水果 : %s' % fruits[index])
	print("完成!")
```

以上代码输出结果：

```python
当前水果 : 香蕉
当前水果 : 苹果
当前水果 : 葡萄
完成!
```

以上实例我们使用了内置函数 len() 和 range(),函数 len() 返回列表的长度，即元素的个数。 range返回一个序列的数。

### 循环

1. 在 python 中，for … else 表示这样的意思，for 中的语句和普通的没有区别，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while … else 也是一样。

```python
for num in range(20,30):  # 迭代 10 到 20 之间的数字  
	for i in range(2,num): # 根据因子迭代
    	if num%i == 0:      # 确定第一个因子 
    		j=num/i          # 计算第二个因子
    		print ('%d 等于 %d * %d' % (num,i,j))
    		break            # 跳出当前循环
    else:                  # 循环的 else 部分
    	print ('%d 是一个质数' % num)
```

以上代码输出结果：

```python
20 等于 2 * 10
21 等于 3 * 7
22 等于 2 * 11
23 是一个质数
24 等于 2 * 12
25 等于 5 * 5
26 等于 2 * 13
27 等于 3 * 9
28 等于 2 * 14
29 是一个质数
```



#### 空心等边三角形

```python
rows = int(input('输入列数： '))
print("打印空心等边三角形，这里去掉if-else条件判断就是实心的")
for i in range(0, rows + 1):#变量i控制行数
    for j in range(0, rows - i):#(1,rows-i)
        print(" ", end='')
        j += 1
    for k in range(0, 2 * i - 1):#(1,2*i)
        if k == 0 or k == 2 * i - 2 or i == rows:
            if i == rows:
                if k % 2 == 0:#因为第一个数是从0开始的，所以要是偶数打印*，奇数打印空格
                    print("*", end='')
                else:
                    print(" ", end='')#注意这里的", end='' "，一定不能省略，可以起到不换行的作用
            else:
               print("*", end='')
        else:
            print(" ", end='')
        k += 1
    print("\
")
    i += 1
```

#### 菱形

```python
rows = int(input('输入列数： '))
print("打印空心等菱形，这里去掉if-else条件判断就是实心的")
rows = int(input('输入列数： '))
for i in range(rows):#变量i控制行数
    for j in range(rows - i):#(1,rows-i)
        print(" ", end='')
        j += 1
    for k in range(2 * i - 1):#(1,2*i)
        if k == 0 or k == 2 * i - 2:
            print("*", end='')
        else:
            print(" ", end='')
        k += 1
    print("\
")
    i += 1
    #菱形的下半部分
for i in range(rows):
    for j in range(i):#(1,rows-i)
        print(" ", end='')
        j += 1
    for k in range(2 * (rows - i) - 1):#(1,2*i)
        if k == 0 or k == 2 * (rows - i) - 2:
            print("*", end='')
        else:
            print(" ", end='')
        k += 1
    print("\
")
    i += 1
```

### 格式化

| 数字       | 格式    | 输出      | 描述                         |
| :--------- | :------ | :-------- | :--------------------------- |
| 3.1415926  | {:.2f}  | 3.14      | 保留小数点后两位             |
| 3.1415926  | {:+.2f} | +3.14     | 带符号保留小数点后两位       |
| -1         | {:+.2f} | -1.00     | 带符号保留小数点后两位       |
| 2.71828    | {:.0f}  | 3         | 不带小数                     |
| 5          | {:0>2d} | 05        | 数字补零 (填充左边, 宽度为2) |
| 5          | {:x<4d} | 5xxx      | 数字补x (填充右边, 宽度为4)  |
| 10         | {:x<4d} | 10xx      | 数字补x (填充右边, 宽度为4)  |
| 1000000    | {:,}    | 1,000,000 | 以逗号分隔的数字格式         |
| 0.25       | {:.2%}  | 25.00%    | 百分比格式                   |
| 1000000000 | {:.2e}  | 1.00e+09  | 指数记法                     |
| 13         | {:>10d} | 13        | 右对齐 (默认, 宽度为10)      |
| 13         | {:<10d} | 13        | 左对齐 (宽度为10)            |
| 13         | {:^10d} | 13        | 中间对齐 (宽度为10)          |

### Python三引号

Python 中三引号可以将复杂的字符串进行赋值。

Python 三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。

三引号的语法是一对连续的单引号或者双引号（通常都是成对的用）。

```python
 >>> hi = '''hi 
 there'''
 >>> hi   # repr()
 'hi\
 there'
 >>> print(hi)  # str()
 
 hi there
```

三引号让程序员从引号和特殊字符串的泥潭里面解脱出来，自始至终保持一小块字符串的格式是所谓的WYSIWYG（所见即所得）格式的。

一个典型的用例是，当你需要一块HTML或者SQL时，这时当用三引号标记，使用传统的转义字符体系将十分费神。

```python
 errHTML = '''
 <HTML><HEAD><TITLE>
 Friends CGI Demo</TITLE></HEAD>
 <BODY><H3>ERROR</H3>
 <B>%s</B><P>
 <FORM><INPUT TYPE=button VALUE=Back
 ONCLICK="window.history.back()"></FORM>
 </BODY></HTML>'''
 
 cursor.execute('''
 CREATE TABLE users (
 login VARCHAR(8), 
 uid INTEGER,prid INTEGER)
 ''')
```

### 列表

```python
list = []          # 空列表
list.append('Google')   # 使用 append() 添加元素
list.append('ShowMeAI')
print(list)
```

以上代码执行结果：

```python
['Google', 'ShowMeAI']
```

| Python 表达式                | 结果                         | 描述                 |
| :--------------------------- | :--------------------------- | :------------------- |
| len([1, 2, 3])               | 3                            | 长度                 |
| [1, 2, 3] + [4, 5, 6]        | [1, 2, 3, 4, 5, 6]           | 组合                 |
| [‘Hi!’] * 4                  | [‘Hi!’, ‘Hi!’, ‘Hi!’, ‘Hi!’] | 重复                 |
| 3 in [1, 2, 3]               | True                         | 元素是否存在于列表中 |
| for x in [1, 2, 3]: print x, | 1 2 3                        | 迭代                 |

| 序号 | 函数      | 作用               |
| :--- | :-------- | :----------------- |
| 1    | len(list) | 列表元素个数       |
| 2    | max(list) | 返回列表元素最大值 |
| 3    | min(list) | 返回列表元素最小值 |
| 4    | list(seq) | 将元组转换为列表   |

| 序号 | 方法                                         | 作用                                                         |
| :--- | :------------------------------------------- | :----------------------------------------------------------- |
| 1    | list.append(obj)                             | 在列表末尾添加新的对象                                       |
| 2    | list.count(obj)                              | 统计某个元素在列表中出现的次数                               |
| 3    | list.extend(seq)                             | 在列表末尾一次性追加另一个序列中的多个值（用新列表扩展原来的列表） |
| 4    | list.index(obj)                              | 从列表中找出某个值第一个匹配项的索引位置                     |
| 5    | list.insert(index, obj)                      | 将对象插入列表                                               |
| 6    | list.pop([index=-1])                         | 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值 |
| 7    | list.remove(obj)                             | 移除列表中某个值的第一个匹配项                               |
| 8    | list.reverse()                               | 反向列表中元素                                               |
| 9    | list.sort(cmp=None, key=None, reverse=False) | 对原列表进行排序                                             |

### 字典

| 判断key-'name'是否存在 | name in a                                                    |
| :--------------------- | :----------------------------------------------------------- |
| 增加某个key--'age'     | a['age'] = 20                                                |
| 获取某个key的值        | a['name']                                                    |
| 获取所有的value        | a.values()                                                   |
| 获取所有的key          | a.keys()                                                     |
| 删除key                | a.pop('name')<br />如果key不存在会报错<br />a.pop('name',0)<br /> 增加默认值，不会报错 |

```python
del dict['Name']  # 删除键是'Name'的条目
dict.clear()      # 清空字典所有条目
del dict          # 删除字典
```

两个重要的点需要记住：

1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会更新前一个，如下实例：

```python
dict = {'Name': 'Zara', 'Age': 7, 'Name': 'ShowMeAI'} print "dict['Name']: ", dict['Name']
```

以上实例输出结果：

```python
dict['Name']:  ShowMeAI
```



2）键必须不可变，所以可以用数字，字符串或元组充当，所以用列表就不行，如下实例：

```python
dict = {['Name']: 'Zara', 'Age': 7}
print("dict['Name']: ", dict['Name'])
```

以上实例输出结果：

```python
Traceback (most recent call last):
File "<string>", line 3, in <module>
TypeError: unhashable type: 'list'
```

#### 字典内置函数与方法

Python字典包含了以下内置函数：

| 函数及描述        | 作用                                               |
| :---------------- | :------------------------------------------------- |
| cmp(dict1, dict2) | 比较两个字典元素。                                 |
| len(dict)         | 计算字典元素个数，即键的总数。                     |
| str(dict)         | 输出字典可打印的字符串表示。                       |
| type(variable)    | 返回输入的变量类型，如果变量是字典就返回字典类型。 |

Python字典包含了以下内置方法：

| 函数及描述                         | 作用                                                         |
| :--------------------------------- | :----------------------------------------------------------- |
| dict.clear()                       | 删除字典内所有元素                                           |
| dict.copy()                        | 返回一个字典的浅复制                                         |
| dict.fromkeys(seq[, val])          | 创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值 |
| dict.get(key, default=None)        | 返回指定键的值，如果值不在字典中返回default值                |
| dict.has_key(key)                  | 如果键在字典dict里返回true，否则返回false                    |
| dict.items()                       | 返回可遍历的(键, 值) 元组数组的视图对象                      |
| dict.keys()                        | 返回一个字典所有的键的视图对象                               |
| dict.setdefault(key, default=None) | 和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default |
| dict.update(dict2)                 | 把字典dict2的键/值对更新到dict里                             |
| dict.values()                      | 返回字典中的所有值的视图对象                                 |
| pop(key[,default])                 | 删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回default值。 |
| popitem()                          | 返回并删除字典中的最后一对键和值。                           |

### 集合内置方法完整列表

| 方法                          | 描述                                                         |
| :---------------------------- | :----------------------------------------------------------- |
| add()                         | 为集合添加元素                                               |
| clear()                       | 移除集合中的所有元素                                         |
| copy()                        | 拷贝一个集合                                                 |
| difference()                  | 返回多个集合的差集                                           |
| difference_update()           | 移除集合中的元素，该元素在指定的集合也存在。                 |
| discard()                     | 删除集合中指定的元素                                         |
| intersection()                | 返回集合的交集                                               |
| intersection_update()         | 返回集合的交集。                                             |
| isdisjoint()                  | 判断两个集合是否包含相同的元素，如果没有返回 True，否则返回 False。 |
| issubset()                    | 判断指定集合是否为该方法参数集合的子集。                     |
| issuperset()                  | 判断该方法的参数集合是否为指定集合的子集                     |
| pop()                         | 随机移除元素                                                 |
| remove()                      | 移除指定元素                                                 |
| symmetric_difference()        | 返回两个集合中不重复的元素集合。                             |
| symmetric_difference_update() | 移除当前集合中在另外一个指定集合相同的元素，并将另外一个指定集合中不同的元素插入到当前集合中。 |
| union()                       | 返回两个集合的并集                                           |
| update()                      | 给集合添加元素                                               |

### 可更改(mutable)与不可更改(immutable)对象

在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。

- **不可变类型：**变量赋值 **a=10** 后再赋值 **a=5**，这里实际是新生成一个 int 值对象 5，再让 a 指向它，而 10 被丢弃，不是改变 a 的值，相当于新生成了 a。
- **可变类型：**变量赋值 **l=[1,2,3,4]** 后再赋值 **l[2]=5** 则是将 list l 的第三个元素值更改，本身l没有动，只是其内部的一部分值被修改了。

**python 函数的参数传递**：

- **不可变类型：**类似 C++ 的值传递，如整数、字符串、元组。如 func(a)，传递的只是 a 的值，没有影响 a 对象本身。如果在 func(a) 内部修改 a 的值，则是新生成一个 a 的对象。
- **可变类型：**类似 C++ 的引用传递，如 列表，字典。如 func(l)，则是将 l 真正的传过去，修改后 func 外部的 l 也会受影响

python 中一切都是对象，严格意义我们不能说值传递还是引用传递，我们应该说传不可变对象和传可变对象。

### 不定长参数

你可能需要一个函数能处理比当初声明时更多的参数。这些参数叫做不定长参数，和上述 2 种参数不同，声明时不会命名。基本语法如下：

```python
def function_name([formal_args,] *var_args_tuple ):
    "函数_文档字符串"   
	function_suite
    return [expression]
```



加了星号 ***** 的参数会以元组(tuple)的形式导入，存放所有未命名的变量参数。

```python
def print_info( arg1, *vartuple ):
    "打印任何传入的参数"
    print("输出: ")  
    print(arg1)   
    print(vartuple)
    
    # 调用print_info 函数print_info( 100, 90, 80 )
```

以上实例输出结果：

```python
输出:
100
(90, 80)
```



如果在函数调用时没有指定参数，它就是一个空元组。我们也可以不向函数传递未命名的变量。

```python
def print_info( arg1, *vartuple ):  
    "打印任何传入的参数" 
    print("输出: ")  
    print(arg1) 
    for var in vartuple:  
        print (var)  
        return
    
# 调用printinfo 函数
print_info( 100 )
print_info( 90, 80, 70 )
```

以上实例输出结果：

```python
输出:100
输出:
90
80
70
```



还有一种就是参数带两个星号 ***\***基本语法如下：

```python
def function_name([formal_args,] **var_args_dict ):  
    "函数_文档字符串" 
	function_suite
    return [expression]
```



加了两个星号 ***\*** 的参数会以字典的形式导入。

```python
def print_info( arg1, **vardict ):  
    "打印任何传入的参数"  
    print("输出: ")  
    print(arg1)  
    print(vardict)
    
# 调用print_info 函数
print_info(1, a=2,b=3)
```

以上实例输出结果：

```python
输出: 1
{'a': 2, 'b': 3}
```



声明函数时，参数中星号 ***** 可以单独出现，例如:

```python
def f(a,b,*,c):  
    return a+b+c
```

如果单独出现星号 ***** 后的参数必须用关键字传入。

```python
def f(a,b,*,c):  
    return a+b+c
f(1,2,c=3) # 正常
f(1,2,3)   # 报错
```

### 迭代器(iterator)与生成器(generator)

#### 迭代器

迭代是Python最强大的功能之一，是访问集合元素的一种方式。

迭代器是一个可以记住遍历的位置的对象。

迭代器对象从集合的第一个元素开始访问，直到所有的元素被访问完结束。迭代器只能往前不会后退。

迭代器有两个基本的方法：**iter()** 和 **next()**。

字符串，列表或元组对象都可用于创建迭代器：

```python
list=[1,2,3,4]
it = iter(list)    # 创建迭代器对象
print(next(it))   # 输出迭代器的下一个元素1
print(next(it))   # 输出迭代器的下一个元素2
```

迭代器对象可以使用常规for语句进行遍历：

```python
l=['Baidu', 'ShowMeAI', 'google', 'ByteDance']
it = iter(l)    # 创建迭代器对象
for x in it: 
	print(x)
```

执行以上程序，输出结果如下：

```python
Baidu
ShowMeAI
google
ByteDance
```

也可以使用 `next()` 函数

```python
list=['Baidu', 'ShowMeAI', 'google', 'ByteDance']
it = iter(list)    # 创建迭代器对象
while True:    
    try:      
        print(next(it))    
    except StopIteration:    
        break
       
```

#### StopIteration

StopIteration 异常用于标识迭代的完成，防止出现无限循环的情况，在 **next**() 方法中我们可以设置在完成指定循环次数后触发 StopIteration 异常来结束迭代。

在 10 次迭代后停止执行：

```python
class IterNumbers:
  def __iter__(self):
    self.a = 1
    return self
  def __next__(self):
    if self.a <= 10:
      x = self.a
      self.a += 1
      return x
    else:
      raise StopIteration
num_class = IterNumbers()
iter_num = iter(num_class)
for x in iter_num:
  print(x)
```

输出结果：

```python
1
2
3
4
5
6
7
8
9
10
> 
```

#### 生成器

在 Python 中，使用了 yield 的函数被称为生成器（generator）。

跟普通函数不同的是，生成器是一个返回迭代器的函数，只能用于迭代操作。

调用一个生成器函数，返回的是一个迭代器对象。

使用yield实现斐波那契：

```python
def fibonacci(n): # 生成器函数 - 斐波那契
    a, b, counter = 0, 1, 0
    while True:
        if (counter > n): 
            return
        yield a
        a, b = b, a + b
        counter += 1
f = fibonacci(10) # f 是一个迭代器，由生成器返回生成
while True:
    try:
        print(next(f))
    except StopIteration:
        break
        
# 输出：
0
1
1
2
3
5
8
13
21
34
55
> 
```





