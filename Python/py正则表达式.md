[Python 正则表达式详解（建议收藏！）_山山而川'的博客-CSDN博客_python正则表达式csdn](https://blog.csdn.net/qq_44159028/article/details/120575621?ops_request_misc=&request_id=&biz_id=102&utm_term=python正则表达式&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-0-120575621.nonecase&spm=1018.2226.3001.4187)

##### compile()函数

编译正则表达式模式，返回一个对象的模式（可以把那些常用的正则表达式编译成正则表达式对象，这样可以提高一点效率）。

格式：`re.compile(pattern,flags=0)`

```py
import retext = "The moment you think about giving up,think of the reason why you held on so long."text1 = "Life is a journey,not the destination,but the scenery along the should be and the mood at the view."rr = re.compile(r'\w*o\w*')print(rr.findall(text))   #查找text中所有包含'o'的单词print(rr.findall(text1))   #查找text1中所有包含'o'的单词
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207700)

- `pattern`： 编译时用的表达式字符串（即正则表达式）；
- `flags`：（可选）编译标志位，用于修改正则表达式的匹配方式，如：是否区分大小写，多行匹配等。常用的`flags`有：

| 标志               | 含义                                                     |
| ------------------ | -------------------------------------------------------- |
| re.S(DOTALL)       | 使.匹配包括换行在内的所有字符                            |
| re.I（IGNORECASE） | 使匹配对大小写不敏感                                     |
| re.L（LOCALE）     | 做本地化识别（locale-aware)匹配，法语等                  |
| re.M(MULTILINE)    | 多行匹配，影响^和$                                       |
| re.X(VERBOSE)      | 该标志通过给予更灵活的格式以便将正则表达式写得更易于理解 |
| re.U               | 根据Unicode字符集解析字符，这个标志影响\w,\W,\b,\B       |

##### match()函数

在字符串刚开始的位置匹配，在开头匹配到目的字符便返回，如果开头没有目的字符将匹配失败，返回`None`。

格式：`re.match(pattern, string, flags=0)`

```py
print(re.match('edu','educoder.net').group())print(re.match('edu','www.educoder.net').group())
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207608)

注：`match()`函数返回的是一个`match object`对象，而`match object`对象有以下方法：

- `group()`：返回被正则匹配的字符串；
- `start()`：返回匹配开始的位置；
- `end()`：返回匹配结束的位置；
- `span()`：返回一个元组包含匹配 (开始，结束) 的位置；
- `groups()`：返回正则整体匹配的字符串，可以一次输入多个组号，对应组号匹配的字符串。

##### search()函数

`re.search()`函数会在字符串内查找模式匹配，只要找到第一个匹配然后返回。如果字符串没有匹配，则返回`None`。

格式：`re.search(pattern, string, flags=0)`

```py
print(re.search('edu','www.educoderedu.net').group())print(re.search('eduaaa','www.educoderedu.net').group())
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207609)

注：`match()`和`search()`比较类似，它们的区别在于`match()`只匹配字符串的开头，如果开头没有出现目的字符串，即使后面出现了也不会进行匹配；`search()`函数会在整个字符内匹配，只要找到一个目的字符串就返回。

##### finditer()函数

搜索字符串，返回一个`Match`对象的迭代器（包含匹配的开始和结束的位置，如下图中的`i`所示）。找到正则匹配的所有子串，把它们作为一个迭代器返回。

格式：`re.finditer(pattern, string, flags=0)`；

```py
itext = re.finditer(r'\d+','12 edueduedu44coder deducoder, 11skdh   ds 12')      #匹配所有的数字for i in itext:    print(i)    print(i.group())    print(i.span())   #span()返回一个元组包含匹配 (开始,结束) 的位置
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207619)

##### split()函数

按照能够匹配的子串，将`string`分割后返回列表。

格式：`re.split(pattern, string)`；

可以使用`re.split`来分割字符串，如：`re.split(r'\s+', text)`将字符串，按空格分割成一个单词列表。

以数字为分割符，将字符串分割：

```py
print(re.split(r'\d+','asas2kdjs4jds5djdfj1djf0'))
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207614)

##### sub()函数

使用`re`替换`string`中每一个匹配的子串后，返回替换后的字符串。

格式：`re.sub(pattern, repl, string, count)`；

用`-`替代`,`如下：

```py
import retext = "aaa,bbb,ccc,ddd"
print(re.sub(r',', '-', text))
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207615)

##### subn()函数

返回替换次数。

格式：`subn(pattern, repl, string, count=0, flags=0)`； 解释：用`A`替换`123`中的`1`，结果为`A23`，`repl`就是指的`A`。

把所有的数字替换为`A`：

```py
print(re.subn('\d','A','1asd2dkjf34'))
```

运行结果如下：

![img](https://data.educoder.net/api/attachments/207617)

`subn()`不仅返回了替换后的字符串，还返回了替换的次数。

 