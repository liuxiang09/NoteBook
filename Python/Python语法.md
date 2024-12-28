[TOC]



# Python

## 基本语法

### python保留字

<img src="C:\Users\LiuXiang\AppData\Roaming\Typora\typora-user-images\image-20221103091635859.png" alt="image-20221103091635859" style="zoom:150%;" />

### print函数

```py
print(*objects, sep=' ', end='\n', file=sys.stdout, flush=False)
```

| 参数      | 描述                                                         |
| --------- | ------------------------------------------------------------ |
| *objects* | 要输出的对象，是复数形式，表示可以一次输出多个对象。输出多个对象时，需要用 , 分隔。 |
| *sep*     | 用来间隔多个对象，默认值是一个空格。                         |
| *end*     | 用来设定以什么结尾。默认值是换行符 \n，我们可以换成其他字符串。 |
| *file*    | 要写入的文件对象，默认是标准输出。                           |
| *flush*   | 输出是否被缓存通常决定于 file，但如果 flush 关键字参数为 True，流会被强制刷新。 |

 ### Python格式化输出

| 占位符 | 说明                                   |
| ------ | -------------------------------------- |
| %d，%i | 转换为带符号的十进制形式的整数         |
| %o     | 转换为带符号的八进制形式的整数         |
| %x，%X | 转换为带符号的十六进制形式的整数       |
| %e     | 转化为科学计数法表示的浮点数（e 小写） |
| %E     | 转化为科学计数法表示的浮点数（E 大写） |
| %f，%F | 转化为十进制形式的浮点数               |
| %g     | 智能选择使用 %f 或 %e 格式             |
| %G     | 智能选择使用 %F 或 %E 格式             |
| %c     | 格式化字符及其 ASCII 码                |
| %r     | 使用 repr() 将变量或表达式转换为字符串 |
| %s     | 使用 str() 将变量或表达式转换为字符串  |

### Python类型转换

| 函数格式            | 使用示例                                       | 描述                                                         |
| ------------------- | ---------------------------------------------- | ------------------------------------------------------------ |
| int(x [,base])      | int(“8”)                                       | 可以转换的包括String类型和其他数字类型，但是会丢失精度       |
| float(x)            | float(1)或者float(“1”)                         | 可以转换String和其他数字类型，不足的位数用0补齐，例如1会变成1.0 |
| complex(real ,imag) | complex(“1”)或者complex(1,2)                   | 第一个参数可以是String或者数字，第二个参数只能为数字类型，第二个参数没有时默认为0 |
| str(x)              | str(1)                                         | 将数字转化为String                                           |
| repr(x)             | repr(Object)                                   | 返回一个对象的String格式                                     |
| eval(str)           | eval(“12+23”)                                  | 执行一个字符串表达式，返回计算的结果,如例子中返回35          |
| tuple(seq)          | tuple((1,2,3,4))                               | 参数可以是元组、列表或者字典，为字典时，返回字典的key组成的集合 |
| list(s)             | list((1,2,3,4))                                | 将序列转变成一个列表，参数可为元组、字典、列表，为字典时，返回字典的key组成的集合 |
| set(s)              | set([‘b’, ‘r’, ‘u’, ‘o’, ‘n’])或者set(“asdfg”) | 将一个可以迭代对象转变为可变集合，并且去重复，返回结果可以用来计算差集x - y、并集x \| y、交集x & y |
| frozenset(s)        | frozenset([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])      | 将一个可迭代对象转变成不可变集合，参数为元组、字典、列表等， |
| chr(x)              | chr(0x30)                                      | chr()用一个范围在 range（256）内的（就是0～255）整数作参数，返回一个对应的字符。返回值是当前整数对应的ascii字符。 |
| ord(x)              | ord(‘a’)                                       | 返回对应的 ASCII 数值，或者 Unicode 数值                     |
| hex(x)              | hex(12)                                        | 把一个整数转换为十六进制字符串                               |
| oct(x)              | oct(12)                                        | 把一个整数转换为八进制字符串                                 |

### is 和 == 的区别

> ==判断的核心是数值是否相同，is判断的核心是地址是否相同

在数值型、字符串、元组中，is和==效果相同

在列表型中，效果不同

## Python内置函数

##### 数学运算

```py
abs()`：返回数值的绝对值； 例如： `>>> abs(-4)` `4
divmod()`：返回两个数值的商和余数； 例如： `>>> divmod(7,2)` `(3,1)
max()`：返回元素中的最大值； 例如： `>>> max(2,6,1,7)` `7
min()`：返回元素中的最小值； 例如： `>>> min(2,6,1,7)` `1
sum()`：返回传入元素之和。 例如： `>>> sum((1,2,3,4))` `10` `>>> sum([1,2,3,4])` `10` `>>> sum((1,2,3,4),-10)` `0
```

##### 类型转换

```py
bool()`：根据传入的参数的逻辑值创建一个新的布尔值； 例如： `>>> bool()` `False` `>>> bool(1)` `True` `>>> bool(0)` `False` `>>> bool('str')` `True
int()`：根据传入的参数创建一个新的整数； 例如： `>>> int('3')` `3` `>>> int('3.6')` `3
float()`：根据传入的参数创建一个新的浮点数； 例如： `>>> float() #不提供参数的时候，返回0.0` `0.0` `>>> float(3)` `3.0` `>>> float('3')` `3.0
complex()`：根据传入的参数创建一个新的复数。 例如： `>>> complex() #当两个参数都不提供时，返回复数0j` `0j` `>>> complex('2+4j')` `(2+4j)` `>>> complex(1,2)` `(1+2j)
```

##### 序列操作

```py
all()`：判断可迭代对象的每个元素是否都为`True`值； 例如： `>>> all([1,2,3]) #列表中每个元素逻辑值均为True，返回True` `True` `>>> all([0,1,2]) #列表中0的逻辑值为False，返回False` `False` `>>> all(()) #空元组` `True
any()`：判断可迭代对象的元素是否有为`True`值的元素； 例如： `>>> any([0,1,2]) #列表元素有一个为True，则返回True` `True` `>>> any([0,0]) #列表元素全部为False，则返回False` `False` `>>> any([]) #空列表` `False
sorted()`：对可迭代对象进行排序，返回一个新的列表。 例如： `>>> a = ['a','b','d','c','B','A']` `>>> a` `['a', 'b', 'd', 'c', 'B', 'A']` `>>> sorted(a) # 默认按字符ascii码排序` `['A', 'B', 'a', 'b', 'c', 'd']
```

##### 对象操作

`help()`：返回对象的帮助信息；

`dir()`：返回对象或者当前作用域内的属性列表。

##### 交互操作

`print()`：向标准输出对象打印输出；

`input()`：读取用户输入值。

##### 文件操作

```py
open()`：使用指定的模式和编码打开文件，返回文件读写对象。 例如： `# t为文本读写，b为二进制读写` `>>> a = open('test.txt','rt')` `>>> a.read()` `'some text'` `>>> a.close()
```

## Python字符串

### 获取字符

> Python 中没有单个字符的概念，单个字符在 Python 中也是字符串类型。我们要获取 Python 字符串中的单个字符，需要使用下标索引的形式，即 `[]`。

Python 规定，字符串中第一个字符的索引为 0、第二个字符的索引为 1，后面各字符依此类推。

Python 也允许从后面开始计算索引，**最后一个字符的索引为 -1，倒数第二个字符的索引为 -2**，依此类推。

### 截取字符串

```python
string[start : end : step]
```

| 参数     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| *string* | 要截取的字符串。                                             |
| *start*  | 表示要截取的第一个字符所在的索引（**截取时包含该字符**）。如果不指定，默认为 0，也就是从字符串的开头截取。 |
| *end*    | 表示要截取的最后一个字符所在的索引（**截取时不包含该字符**）。如果不指定，默认为字符串的长度。 |
| *step*   | 指的是从 start 索引处的字符开始，每 step 个距离获取一个字符，直至 end 索引出的字符。step 默认值为 1，当省略该值时，最后一个冒号也可以省略。 |

### 拼接字符串

1. 写在一起
2. 用 '+' 号

### 获取字符串长度

`len(string)`，返回值为int类型

### 分割字符串

`str.split(sep, maxsplit)`

> 返回值为一个列表
>
> 如果不指定sep参数， 那么也不能指定maxsplit参数

| 参数       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| *str*      | 表示要进行分割的字符串。                                     |
| *sep*      | 用于指定分隔符，可以包含多个字符。此参数默认为 None，表示所有空字符，包括空格、换行符“\n”、制表符“\t”等。 |
| *maxsplit* | 可选参数，用于指定分割的次数，最后列表中子串的个数最多为 maxsplit+1。如果不指定或者指定为 -1，则表示分割次数没有限制。 |

### 合并字符串

> 在开发过程中，很多时候我们有合并 **[字符串](https://haicoder.net/python/python-string.html)** 的需求，即把一个 **[元祖](https://haicoder.net/python/python-tuple.html)** 或 **[列表](https://haicoder.net/python/python-list.html)** 中包含的多个字符串连接成一个字符串。这个操作是 **[分割字符串](https://haicoder.net/python/python-string-split.html)** 的逆操作。

```py
strResult = str.join(iterable)
```

| 参数       | 描述                                                   |
| ---------- | ------------------------------------------------------ |
| *str*      | 用于指定合并时的分隔符。                               |
| *iterable* | 做合并操作的源字符串数据，允许以列表、元组等形式提供。 |

### 统计字符出现次数

> count() 函数返回 **[int](https://haicoder.net/python/python-int.html)** 类型的值，如果检索的字符串不存在，则返回 0，否则返回出现的次数。

```py
S.count(sub[, start[, end]]) -> int
# []表示可写可不写
```

| 参数    | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| *S*     | 表示原字符串。                                               |
| *sub*   | 表示要检索的字符串。                                         |
| *start* | 指定检索的起始位置，也就是从什么位置开始检测。如果不指定，默认从头开始检索。 |
| *end*   | 指定检索的终止位置，如果不指定，则表示一直检索到结尾。       |

### 查找字符串

> find() 函数返回 **[int](https://haicoder.net/python/python-int.html)** 类型的值，如果包含，则返回第一次出现该字符串的索引；反之，则**返回 -1**。

```py
S.find(sub[, start[, end]]) -> int
```

| 参数    | 说明                                                       |
| ------- | ---------------------------------------------------------- |
| *s*     | 表示原字符串。                                             |
| *sub*   | 表示要检索的字符串。                                       |
| *start* | 表示开始检索的起始位置。如果不指定，则默认从头开始检索。   |
| *end*   | 表示结束检索的结束位置。如果不指定，则默认一直检索到结尾。 |

### 查找字符串位置

> index() 函数返回 **int** 类型的值，如果找到，则返回第一次出现该字符串的索引；反之，则**抛出异常**。

```py
S.index(sub[, start[, end]]) -> int
```

| 参数    | 说明                                                       |
| ------- | ---------------------------------------------------------- |
| *s*     | 表示原字符串。                                             |
| *sub*   | 表示要检索的字符串。                                       |
| *start* | 表示开始检索的起始位置。如果不指定，则默认从头开始检索。   |
| *end*   | 表示结束检索的结束位置。如果不指定，则默认一直检索到结尾。 |

### 字符串对齐

```py
S.ljust(width[, fillchar]) -> str	# 左对齐
S.rjust(width[, fillchar]) -> str	# 右对齐
S.center(width[, fillchar]) -> str	# 居中对齐
```

| 参数       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| *s*        | 表示要进行填充的字符串。                                     |
| *width*    | 表示包括 S 本身长度在内，字符串要占的总长度。                |
| *fillchar* | 作为可选参数，用来指定填充字符串时所用的字符，默认情况使用空格。 |
| *end*      | 表示结束检索的结束位置。如果不指定，则默认一直检索到结尾。   |

### 字符串开始和结尾

```py
S.startswith(prefix[, start[, end]]) -> bool
S.endswith(suffix[, start[, end]]) -> bool
```

| 参数     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| *s*      | 表示原字符串。                                               |
| *prefix* | 要检索的子串。                                               |
| *start*  | 指定检索开始的起始位置索引，如果不指定，则默认从头开始检索。 |
| *end*    | 表示结束检索的结束位置。如果不指定，则默认一直检索到结尾。   |

### 首字母大写

```py
S.title() -> str
str.istitle() -> bool	# 是否首字母大写其它字母小写
```

### 大小写转换

```py
S.lower() -> str	# 大写转小写
S.upper() -> str	# 小写转大写
str.islower() -> bool	# 是否小写
str.isupper() -> bool	# 是否大写
```

### 是否是数字字母

> isnumeric() 函数只能判断 unicode 字符串，我们如果需要定义一个字符串为 Unicode 形式，只要在字符串前添加 ‘u’ 前缀即可。
>
> isdecimal() 函数只能判断 unicode 字符串，我们如果需要定义一个字符串为 Unicode 形式，只要在字符串前添加 ‘u’ 前缀即可。

```py
str.isnumeric() -> bool
str.isdigit() -> bool
str.isdecimal() -> bool
str.isalnum() -> bool	# 是否只有字母和数字
str.isalpha() -> bool	# 是只有字母
str.isspace() -> bool	# 是否是空格
```

#### isdecimal() isdigit() isnumeric()比较

| 函数          | 描述                                                         |
| ------------- | ------------------------------------------------------------ |
| *isdecimal()* | 是否为十进制数字符，包括 Unicode 数字、双字节全角数字，不包括罗马数字、汉字数字、小数。 |
| *isdigit()*   | 是否为数字字符，包括 Unicode 数字，单字节数字，双字节全角数字，不包括汉字数字，罗马数字、小数。 |
| *isnumeric()* | 是否所有字符均为数值字符，包括 Unicode 数字、双字节全角数字、罗马数字、汉字数字，不包括小数。 |

### 去除字符串两侧的空格

> strip意味剥去外皮，所以此函数只能针对两边或者单侧进行清除，不能清楚中间的字符

```py
S.strip([chars]) -> str
S.lstrip([chars]) -> str	# 去除左边空格
S.rstrip([chars]) -> str	# 去除右边空格
```

### 替换字符串

```py
str.replace(old, new[, max])
```

| 参数  | 描述                              |
| ----- | --------------------------------- |
| *str* | 需要替换的原字符串。              |
| *old* | 将被替换的子字符串。              |
| *new* | 新字符串，用于替换 old 子字符串。 |
| *max* | 可选字符串, 替换不超过 max 次。   |

## Python流程控制

### 条件语句

```py
if condition:
    # do something
elif condition1:
    # do something1
elif condition2:
    # do something2
else condition3:
    # do something3
```

### 循环语句

```py
for iterating_var in sequence:
   statements(s)
```

| 参数            | 描述                         |
| --------------- | ---------------------------- |
| *for*           | for 循环使用的关键字。       |
| *iterating_var* | for 循环每次迭代使用的变量。 |
| *in*            | for 循环使用的关键字。       |
| *sequence*      | for 循环需要遍历的变量。     |
| *statements*    | 每次循环执行的逻辑。         |

### while循环

```py
while cond：
    # do something
```

### for else语句

```py
# for...else...语句
for iterating_var in sequence:
   statements(s)
else:
   statements1(s)
# while...else...语句
while cond:
   statements(s)
else:
   statements1(s)
```

如果 for 循环**不是**被 break 语句终止执行的，那么 statements1 的代码**会**正常执行，但如果 for 循环**是**被 break 语句终止执行的，那么 statements1 的代码**不会**正常执行。

## Python集合类

### 列表

> 与数组类似，但是可以存储不同数据类型的元素

#### 创建列表

使用 [] 即可创建列表，并且列表的元素类型可以不一致

#### 访问列表元素

使用下标索引访问

```py
# 使用下标索引的形式，可以访问列表元素
lis = ["Hello", "HaiCoder", 1024]
print(lis[0], lis[1], lis[2])
```

#### 添加元素

###### append函数

> 将元素 obj （或列表等）添加到列表 listname 的结尾处。
>
> 使用 **[append](https://haicoder.net/python/python-list-append.html)** 函数，将一个 **[列表](https://haicoder.net/python/python-list.html)** 或者 **[元祖](https://haicoder.net/python/python-tuple.html)** 添加到列表尾部，那么这个列表或者元祖会被当做是一个元素被整体添加进列表。

```py
listname.append(obj)
```

| 参数       | 描述               |
| ---------- | ------------------ |
| *listname* | 需要添加的列表。   |
| *obj*      | 需要被添加的元素。 |

```py
# 使用 append 函数，向列表中添加一个元素
lis = ["Hello", "HaiCoder", 1024]
lis.append("嗨客网")
print(lis)
# 使用 append 函数，向列表中添加一个列表
lis = ["Hello", "HaiCoder", 1024]
list2 = ["Python", "Golang", "JavaScript"]
lis.append(list2)
print(lis)
# 使用 append 函数，向列表中添加一个元祖
lis = ["Hello", "HaiCoder", 1024]
tup2 = ("Python", "Golang", "JavaScript")
lis.append(tup2)
print(lis)
```

![04 python列表添加元素append.png](https://haicoder.net/uploads/pic/server/python/python-collection/04%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0append.png)

![05 python列表添加元素append.png](https://haicoder.net/uploads/pic/server/python/python-collection/05%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0append.png)

![06 python列表添加元素append.png](https://haicoder.net/uploads/pic/server/python/python-collection/06%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0append.png)

###### extend函数

> 使用 extend 函数，将一个列表或者元祖添加到列表尾部，那么这个列表或者元祖的所有元素都会一个个的添加进列表，而不是当做一个整体。

```py
listname.extend(obj)
```

| 参数       | 描述               |
| ---------- | ------------------ |
| *listname* | 需要添加的列表。   |
| *obj*      | 需要被添加的元素。 |

```py
# 使用 extend 函数，向列表中添加一个元素
lis = ["Hello", "HaiCoder", 1024]
lis.extend("嗨客网")
print(lis)
# 使用 extend 函数，向列表中添加一个列表
lis = ["Hello", "HaiCoder", 1024]
list2 = ["Python", "Golang", "JavaScript"]
lis.extend(list2)
print(lis)
# 使用 extend 函数，向列表中添加一个元祖
lis = ["Hello", "HaiCoder", 1024]
tup2 = ("Python", "Golang", "JavaScript")
lis.extend(tup2)
print(lis)
```

![07 python列表添加元素extend.png](https://haicoder.net/uploads/pic/server/python/python-collection/07%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0extend.png)

![08 python列表添加元素extend.png](https://haicoder.net/uploads/pic/server/python/python-collection/08%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0extend.png)

![09 python列表添加元素extend.png](https://haicoder.net/uploads/pic/server/python/python-collection/09%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0extend.png)

###### insert函数

> 在 **[Python](https://haicoder.net/python/python-tutorial.html)** 中，我们使用 **[append](https://haicoder.net/python/python-list-append.html)** 函数，或者 **[extend](https://haicoder.net/python/python-slots-extends.html)** 函数将元素、**[列表](https://haicoder.net/python/python-list.html)** 或者 **[元祖](https://haicoder.net/python/python-tuple.html)** 添加进列表时，只能添加到列表的**尾部**。
>
> 如果我们需要在列表的**指定索引处**添加元素，那么就需要使用 insert 函数。

```py
listname.insert(index , obj)
```

| 参数       | 描述                       |
| ---------- | -------------------------- |
| *listname* | 需要添加元素的列表。       |
| *index*    | 元素将元素添加的索引位置。 |
| *obj*      | 需要被添加的元素。         |

```py
# 使用 insert 函数，向列表的指定索引处添加一个元素
lis = ["Hello", "HaiCoder", 1024]
lis.insert(2, "嗨客网")
print(lis)
# 使用 insert 函数，向列表中添加一个列表
lis = ["Hello", "HaiCoder", 1024]
list2 = ["Python", "Golang", "JavaScript"]
lis.insert(2, list2)
print(lis)
# 使用 insert 函数，向列表中添加一个元祖
lis = ["Hello", "HaiCoder", 1024]
tup2 = ("Python", "Golang", "JavaScript")
lis.insert(2, tup2)
print(lis)
```

![10 python列表添加元素insert.png](https://haicoder.net/uploads/pic/server/python/python-collection/10%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0insert.png)

![11 python列表添加元素insert.png](https://haicoder.net/uploads/pic/server/python/python-collection/11%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0insert.png)

![11 python列表添加元素insert.png](https://haicoder.net/uploads/pic/server/python/python-collection/11%20python%E5%88%97%E8%A1%A8%E6%B7%BB%E5%8A%A0%E5%85%83%E7%B4%A0insert.png)

#### 删除元素

###### remove函数

> 将元素 element 从列表 listname 中删除，如果元素 element 不存在，则会**抛出异常**，如果有多个 element 元素，则只会删除第一个。

```py
listname.remove(element)
```

| 参数       | 描述                 |
| ---------- | -------------------- |
| *listname* | 需要删除元素的列表。 |
| *element*  | 需要被删除的元素。   |

```py
# 使用 remove 函数，从列表中删除一个元素
lis = ["Hello", "HaiCoder", 1024]
lis.remove("HaiCoder")
print(lis)
# 使用 remove 函数，从列表中删除一个不存在的元素，会报异常
lis = ["Hello", "HaiCoder", 1024]
lis.remove("HaiCoder")
lis.remove("HaiCoder")
print(lis)
# 使用 remove 函数，从列表中删除元素
lis = ["Hello", "HaiCoder", "HaiCoder", 1024]
lis.remove("HaiCoder")
print(lis)
```

![13 python列表删除元素remove.png](https://haicoder.net/uploads/pic/server/python/python-collection/13%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0remove.png)

![14 python列表删除元素remove.png](https://haicoder.net/uploads/pic/server/python/python-collection/14%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0remove.png)

![15 python列表删除元素remove.png](https://haicoder.net/uploads/pic/server/python/python-collection/15%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0remove.png)

###### del函数

> 在 **[Python](https://haicoder.net/python/python-tutorial.html)** 中，如果要根据元素索引删除元素，需要使用 del 语句。del 语句是 Python 中专门用于执行删除操作的语句，不仅可用于删除 **[列表](https://haicoder.net/python/python-list.html)** 的元素，也可用于删除 **[变量](https://haicoder.net/python/python-variable.html)** 等。

```py
# 使用 del 语句，从列表中删除一个元素
lis = ["Hello", "HaiCoder", 1024]
del lis[1]
print(lis)
# 使用 del 语句，从列表中删除多个元素
lis = ["Hello", "HaiCoder", 1024]
del lis[1:3]
print(lis)
# 使用 del 语句，从列表中删除一个不存在的元素，会报异常
lis = ["Hello", "HaiCoder", 1024]
del lis[3]
print(lis)
# 使用 del 语句，删除整个列表
lis = ["Hello", "HaiCoder", 1024]
del lis
print(lis)
# 使用 del 语句，清空整个列表
lis = ["Hello", "HaiCoder", 1024]
del lis[:]
print(lis)
```

![16 python列表删除元素del.png](https://haicoder.net/uploads/pic/server/python/python-collection/16%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0del.png)

![17 python列表删除元素del.png](https://haicoder.net/uploads/pic/server/python/python-collection/17%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0del.png)

![18 python列表删除元素del.png](https://haicoder.net/uploads/pic/server/python/python-collection/18%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0del.png)

![19 python列表删除元素del.png](https://haicoder.net/uploads/pic/server/python/python-collection/19%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0del.png)

![20 python列表删除元素del.png](https://haicoder.net/uploads/pic/server/python/python-collection/20%20python%E5%88%97%E8%A1%A8%E5%88%A0%E9%99%A4%E5%85%83%E7%B4%A0del.png)





###### clear函数

> 在 **[Python](https://haicoder.net/python/python-tutorial.html)** 中，如果要清除 **[列表](https://haicoder.net/python/python-list.html)** 的所有内容，除了可以使用 **[del](https://haicoder.net/python/python-list-del.html)** 语句加上切片的形式，Python 的 list 还专门提供了一个 clear 函数。

```py
# 使用 clear 函数，清空列表元素
lis = ["Hello", "HaiCoder", 1024]
lis.clear()
print(lis)
# 使用 clear 函数，清空空列表，不会报错
lis = ["Hello", "HaiCoder", 1024]
lis.clear()
lis.clear()
print(lis)
```

![21 python列表清空元素clear.png](https://haicoder.net/uploads/pic/server/python/python-collection/21%20python%E5%88%97%E8%A1%A8%E6%B8%85%E7%A9%BA%E5%85%83%E7%B4%A0clear.png)![22 python列表清空元素clear.png](https://haicoder.net/uploads/pic/server/python/python-collection/22%20python%E5%88%97%E8%A1%A8%E6%B8%85%E7%A9%BA%E5%85%83%E7%B4%A0clear.png)

#### 修改元素

> **[Python](https://haicoder.net/python/python-tutorial.html)** 的 **[列表](https://haicoder.net/python/python-list.html)** 的每一个元素都相当于是一个 **[变量](https://haicoder.net/python/python-variable.html)**，因此我们对列表元素的修改可以直接使用索引加上赋值的形式。
>
> 我们使用索引赋值的形式，不仅可以对列表的单个元素执行修改操作，还可以对列表的一段元素执行修改操作。

##### 修改单个元素

```py
lis[index] = value
```

| 参数    | 描述                     |
| ------- | ------------------------ |
| *lis*   | 需要修改元素的列表。     |
| *index* | 需要被修改的元素的索引。 |
| *value* | 需要被修改的值。         |

##### 修改一段元素

```py
lis[index:index2] = [value, value2, ...]
```

| 参数     | 描述                                 |
| -------- | ------------------------------------ |
| *lis*    | 需要被修改的列表。                   |
| *index*  | 需要被修改的开始索引。               |
| *index2* | 需要被修改的结束索引。               |
| *value*  | 需要被修改的开始索引处的值。         |
| *value2* | 需要被修改的开始索引后一个元素的值。 |

```py
# 将列表索引为 1 的位置的元素的值设置为 haicoder
lis = ["Hello", "HaiCoder", 1024]
lis[1] = "haicoder"
print(lis)
# 修改列表多个位置的元素值
lis = ["Hello", "HaiCoder", 1024]
lis[1:3] = ["haicoder", 1111]
print(lis)
```

![23 python列表修改元素值.png](https://haicoder.net/uploads/pic/server/python/python-collection/23%20python%E5%88%97%E8%A1%A8%E4%BF%AE%E6%94%B9%E5%85%83%E7%B4%A0%E5%80%BC.png)![24 python列表修改元素值.png](https://haicoder.net/uploads/pic/server/python/python-collection/24%20python%E5%88%97%E8%A1%A8%E4%BF%AE%E6%94%B9%E5%85%83%E7%B4%A0%E5%80%BC.png)

##### 插入元素

> 如果我们修改的索引数小于后面的列表的元素数，那么就会将所有元素插入

```py
# 如果我们修改的索引数小于后面的列表的元素数，那么就会将所有元素插入
lis = ["Hello", "HaiCoder", 1024]
lis[1:3] = ["haicoder", "嗨客网", "HaiCoder"]
print(lis)
```

![25 python列表修改元素值.png](https://haicoder.net/uploads/pic/server/python/python-collection/25%20python%E5%88%97%E8%A1%A8%E4%BF%AE%E6%94%B9%E5%85%83%E7%B4%A0%E5%80%BC.png)

##### 删除元素

> 如果我们修改的索引数大于后面的列表的元素数，那么就会将多余的索引处元素删除

```py
# 如果我们修改的索引数大于后面的列表的元素数，那么就会将多余的索引处元素删除
lis = ["Hello", "HaiCoder", 1024]
lis[1:3] = ["haicoder"]
print(lis)
```

![26 python列表修改元素值.png](https://haicoder.net/uploads/pic/server/python/python-collection/26%20python%E5%88%97%E8%A1%A8%E4%BF%AE%E6%94%B9%E5%85%83%E7%B4%A0%E5%80%BC.png)

#### count函数

> 在 **[Python](https://haicoder.net/python/python-tutorial.html)** 中，我们需要统计一个元素在 **[列表](https://haicoder.net/python/python-list.html)** 中出现的次数，使用 count 函数。

```py
# 使用 count 函数，统计列表中元素出现次数
lis = ["Hello", "HaiCoder", 1024]
count = lis.count("HaiCoder")
print("Count =", count)
# 使用 count 函数，统计列表中不存在的元素出现次数
lis = ["Hello", "HaiCoder", 1024]
count = lis.count("haicoder")
print("Count =", count)
```

![27 python列表元素出现次数.png](https://haicoder.net/uploads/pic/server/python/python-collection/27%20python%E5%88%97%E8%A1%A8%E5%85%83%E7%B4%A0%E5%87%BA%E7%8E%B0%E6%AC%A1%E6%95%B0.png)![28 python列表元素出现次数.png](https://haicoder.net/uploads/pic/server/python/python-collection/28%20python%E5%88%97%E8%A1%A8%E5%85%83%E7%B4%A0%E5%87%BA%E7%8E%B0%E6%AC%A1%E6%95%B0.png)

#### index函数

>  在 **[Python](https://haicoder.net/python/python-tutorial.html)** 中，我们在 **[列表](https://haicoder.net/python/python-list.html)** 中查找元素出现的位置，使用列表的 **[index](https://haicoder.net/python/python-list-index.html)** 函数，如果找到，返回元素**第一次**出现的索引，如果元素不存在，**报错**。

```
listname.index(obj,start,end)
```

| 参数       | 描述                                       |
| ---------- | ------------------------------------------ |
| *listname* | 需要查找的列表。                           |
| *obj*      | 需要查找的元素。                           |
| *start*    | 可选，需要查找的开始索引，默认为 0。       |
| *end*      | 可选，需要查找的结束索引，默认为列表长度。 |

```py
# 使用 index 函数，在列表中查找元素
lis = ["Hello", "HaiCoder", 1024]
index = lis.index("HaiCoder")
print("index =", index)

# 使用 index 函数，在列表指定范围内查找元素
lis = ["Hello", "HaiCoder", 1024]
index = lis.index(1024, 0, 2)
print("index =", index)

# 使用 index 函数，在列表指定范围内查找元素
lis = ["Hello", "HaiCoder", 1024, "HaiCoder"]
index = lis.index("HaiCoder")
print("index =", index)
```

![29 python列表查找元素.png](https://haicoder.net/uploads/pic/server/python/python-collection/29%20python%E5%88%97%E8%A1%A8%E6%9F%A5%E6%89%BE%E5%85%83%E7%B4%A0.png)![30 python列表查找元素.png](https://haicoder.net/uploads/pic/server/python/python-collection/30%20python%E5%88%97%E8%A1%A8%E6%9F%A5%E6%89%BE%E5%85%83%E7%B4%A0.png)![31 python列表查找元素.png](https://haicoder.net/uploads/pic/server/python/python-collection/31%20python%E5%88%97%E8%A1%A8%E6%9F%A5%E6%89%BE%E5%85%83%E7%B4%A0.png)

#### pop函数

> 在 **[Python](https://haicoder.net/python/python-tutorial.html)** 中，我们在 **[列表](https://haicoder.net/python/python-list.html)** 中弹出一个元素或者 **[删除](https://haicoder.net/python/python-list-del.html)** 指定索引的元素，使用列表的 pop 函数。pop 函数会返回被弹出的元素。
>
> 如果我们使用 pop 函数，弹出列表中的元素的索引不存在，那么程序会报错。
>
> 如果不传 index，默认删除**最后**一个元素，否则，删除索引为 index 处的元素，返回被删除的元素。

```
element = listname.pop(index)
```

| 参数       | 描述                                     |
| ---------- | ---------------------------------------- |
| *listname* | 需要被弹出元素的列表。                   |
| *index*    | 可选，需要弹出的索引，默认为列表的长度。 |
| *element*  | 弹出的元素。                             |

```py
# 使用 pop 函数，删除列表最后一个元素
lis = ["Hello", "HaiCoder", 1024]
element = lis.pop()
print("element =", element, "lis =", lis)

# 使用 pop 函数，弹出列表中指定索引处元素
lis = ["Hello", "HaiCoder", 1024]
element = lis.pop(1)
print("element =", element, "lis =", lis)

# 使用 pop 函数，弹出索引不存在的元素
lis = ["Hello", "HaiCoder", 1024]
element = lis.pop(10)
print("element =", element, "lis =", lis)
```

![32 python列表弹出元素.png](https://haicoder.net/uploads/pic/server/python/python-collection/32%20python%E5%88%97%E8%A1%A8%E5%BC%B9%E5%87%BA%E5%85%83%E7%B4%A0.png)![33 python列表弹出元素.png](https://haicoder.net/uploads/pic/server/python/python-collection/33%20python%E5%88%97%E8%A1%A8%E5%BC%B9%E5%87%BA%E5%85%83%E7%B4%A0.png)![34 python列表弹出元素.png](https://haicoder.net/uploads/pic/server/python/python-collection/34%20python%E5%88%97%E8%A1%A8%E5%BC%B9%E5%87%BA%E5%85%83%E7%B4%A0.png)

#### reverse函数

> 将列表 listname 反转，该函数不返回任何值，而是在原来的列表上做修改。

```py
# 使用 reverse 函数，反转列表
lis = ["Hello", "HaiCoder", 1024]
lis.reverse()
print("reverseList =", lis)
```

![35 python列表反转.png](https://haicoder.net/uploads/pic/server/python/python-collection/35%20python%E5%88%97%E8%A1%A8%E5%8F%8D%E8%BD%AC.png)

#### sort函数

[Python中的sort()使用方法_落凡尘.的博客-CSDN博客_python sort](https://blog.csdn.net/memory_qianxiao/article/details/80548203?ops_request_misc=&request_id=&biz_id=102&utm_term=pythonsort&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-0-80548203.142^v63^js_top,201^v3^control_2,213^v1^control&spm=1018.2226.3001.4187)

> 将列表 listname 排序，该 **[函数](https://haicoder.net/python/python-function.html)** 不返回任何值，而是在原来的列表上做修改。
>
> **[Python](https://haicoder.net/python/python-tutorial.html)** 的 **[列表](https://haicoder.net/python/python-list.html)** 排序我们还可以使用 key 参数，指定系统内置的 **[函数](https://haicoder.net/python/python-function.html)**，做为排序的依据，同时，还可以使用自定义函数，按照自定义规则进行排序。

| 参数       | 描述                                                         |
| ---------- | ------------------------------------------------------------ |
| *listname* | 需要排序的列表。                                             |
| *key*      | 排序规则的函数，可以是系统内置的函数，也可以是自定义函数。   |
| *reverse*  | reverse 参数用于设置是否需要反转排序，默认 **False** 表示从小到大排序；如果将该参数设为 True，将会改为从大到小排序。 |

```py
# 使用 sort 函数，排序列表
lis = ["Hello", "HaiCoder", "haicoder"]
lis.sort()
print("sortedList =", lis)

# 使用 sort 函数，倒叙排序列表
lis = ["Hello", "HaiCoder", "haicoder"]
lis.sort(reverse=True)
print("sortedList =", lis)

# 使用 sort 函数，排序列表元素不可比较，报错
lis = ["Hello", "HaiCoder", 1024]
lis.sort()
print("sortedList =", lis)

# 使用 sort 函数，忽略大小写排序列表
lis = ["Hello", "HaiCoder", "haicoder", "hello"]
lis.sort(key=str.lower)
print("sortedList =", lis)

# 使用 sort 函数，按字符串长度排序列表
lis = ["Hello", "HaiCoder", "Hai", "Code"]
lis.sort(key=len)
print("sortedList =", lis)

# 使用 sort 函数，按字符串长度倒叙排序列表
lis = ["Hello", "HaiCoder", "Hai", "Code"]
lis.sort(key=len, reverse=True)
print("sortedList =", lis)

# 使用 sort 函数，用自定义函数排序列表
def sort_str(str1):
    return str1[1]

lis = ["Code", "Ai", "Hello", "HaiCoder"]
lis.sort(key=sort_str)
print("sortedList =", lis)
```

![36 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/36%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)![37 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/37%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)![38 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/38%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)![39 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/39%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)![40 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/40%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)![41 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/41%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)![42 python列表排序.png](https://haicoder.net/uploads/pic/server/python/python-collection/42%20python%E5%88%97%E8%A1%A8%E6%8E%92%E5%BA%8F.png)

- #### 对于自定义函数

首先，我们自定义了一个函数 sort_str，该函数接受一个字符串类型的 **[变量](https://haicoder.net/python/python-variable.html)**，在该函数里面我们指定排序规则为按照字符串的第二个字符进行排序。

我们在排序列表时，指定了 key 为我们自定义的 sort_str 函数，最后打印结果，我们发现，整个 list 中所有的元素都是按照了字符串的第二个字符进行了排序。

#### range函数

> **[Python](https://haicoder.net/python/python-tutorial.html)** 的内置函数 range() 可创建一个整数 **[列表](https://haicoder.net/python/python-list.html)**，一般在 **[for](https://haicoder.net/python/python-for.html)** 循环中使用。

```
range(start, stop[, step])
```

| 参数    | 描述                                 |
| ------- | ------------------------------------ |
| *start* | 计数从 start 开始。默认是从 0 开始。 |
| *stop*  | 计数到 stop 结束，但不包括 stop。    |
| *step*  | 步长，默认为1，可以支持负数。        |

```py
# 使用 range 函数，生成数列
for value in range(1, 5):
    print(value)
    
# 使用 range 函数，start参数默认从 0 开始
for value in range(3):
    print(value)
    
# 使用 range 函数的 step 参数，可以设置 range 的步长
for value in range(1, 20, 5):
    print(value)
    
# 使用 range 函数的 step 参数，可以设置 range 的步长为负数
for value in range(20, 1, -5):
    print(value)
    
# 使用 range 函数可以遍历字符串
str_hai = "coder"
for i in range(len(str_hai)):
    print(str_hai[i])
```

- #### range函数生成列表

> **[Python](https://haicoder.net/python/python-tutorial.html)** 的内置函数 **[range()](https://haicoder.net/python/python-range.html)** 的默认返回值的类型并不是 **[列表](https://haicoder.net/python/python-list.html)**，如果我们需要使用列表，必须要进行 **[类型转换](https://haicoder.net/python/python-string-bytes.html)**。

```py
# 使用 type 函数，获取range返回类型
range_list = range(5)
print(type(range_list))
lis = list(range_list)
print(type(lis))

# 使用 range 生成列表
lis = []
for value in range(1, 11):
    num = value**2
    lis.append(num)
print(lis)
```

![48 python range函数.png](https://haicoder.net/uploads/pic/server/python/python-collection/48%20python%20range%E5%87%BD%E6%95%B0.png)

![49 python range函数.png](https://haicoder.net/uploads/pic/server/python/python-collection/49%20python%20range%E5%87%BD%E6%95%B0.png)

#### list遍历

> **[Python](https://haicoder.net/python/python-tutorial.html)** 的 **[列表](https://haicoder.net/python/python-list.html)** 的遍历有四种方法：使用 **[for循环](https://haicoder.net/python/python-for.html)** 遍历、使用 **[range](https://haicoder.net/python/python-range.html)** 遍历、使用 enumerate 遍历以及使用 iter 遍历。

```py
# 使用 Python for循环遍历列表
lis = ["Hello", "HaiCoder", 1024]
for item in lis:
    print("Item =", item)

# 使用 Python range遍历列表
lis = ["Hello", "HaiCoder", 1024]
for index in range(len(lis)):
    print("index =", index, "value =", lis[index])
    
# 使用 Python enumerate遍历列表
lis = ["Hello", "HaiCoder", 1024]
for index, value in enumerate(lis):
    print("index =", index, "value =", value)
    
# 使用 Python iter遍历列表
lis = ["Hello", "HaiCoder", 1024]
for value in iter(lis):
    print("value =", value)
```











### 元组	

### 字典

### 集合
