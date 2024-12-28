[TOC]



# STL

## C++迭代器

### 前向迭代器（forward iterator）

> 假设 p 是一个前向迭代器，则 p 支持 ++p，p++，*p 操作，还可以被复制或赋值，可以用 == 和 != 运算符进行比较。此外，两个正向迭代器可以互相赋值。

### 双向迭代器（bidirectional iterator）

> 双向迭代器具有正向迭代器的全部功能，除此之外，假设 p 是一个双向迭代器，则还可以进行 --p 或者 p-- 操作（即一次向后移动一个位置）。

### 随机访问迭代器（random access iterator）

> 随机访问迭代器具有双向迭代器的全部功能。除此之外，假设 p 是一个随机访问迭代器，i 是一个整型变量或常量，则 p 还支持以下操作：

| 操作 | 描述                             |
| ---- | -------------------------------- |
| p+=i | 使得 p 往后移动 i 个元素。       |
| p-=i | 使得 p 往前移动 i 个元素。       |
| p+i  | 返回 p 后面第 i 个元素的迭代器。 |
| p-i  | 返回 p 前面第 i 个元素的迭代器。 |
| p[i] | 返回 p 后面第 i 个元素的引用。   |

此外，两个随机访问迭代器 p1、p2 还可以用 <、>、<=、>= 运算符进行比较。另外，表达式 p2-p1 也是有定义的，其返回值表示 p2 所指向元素和 p1 所指向元素的序号之差（也可以说是 p2 和 p1 之间的元素个数减一）。

### STL迭代器类型

| 容器                               | 对应的迭代器类型 |
| ---------------------------------- | ---------------- |
| array                              | 随机访问迭代器   |
| vector                             | 随机访问迭代器   |
| deque                              | 随机访问迭代器   |
| list                               | 双向迭代器       |
| set / multiset                     | 双向迭代器       |
| map / multimap                     | 双向迭代器       |
| forward_list                       | 前向迭代器       |
| unordered_map / unordered_multimap | 前向迭代器       |
| unordered_set / unordered_multiset | 前向迭代器       |
| stack                              | 不支持迭代器     |
| queue                              | 不支持迭代器     |

### 迭代器定义方式

| 迭代器定义方式 | 具体格式                                   |
| -------------- | ------------------------------------------ |
| 正向迭代器     | 容器类名::iterator 迭代器名;               |
| 常量正向迭代器 | 容器类名::const_iterator 迭代器名;         |
| 反向迭代器     | 容器类名::reverse_iterator 迭代器名;       |
| 常量反向迭代器 | 容器类名::const_reverse_iterator 迭代器名; |

通过定义以上几种迭代器，就可以读取它指向的元素，`*迭代器名` 就表示迭代器指向的元素。其中，常量迭代器和非常量迭代器的分别在于，通过非常量迭代器还能修改其指向的元素。另外，反向迭代器和正向迭代器的**区别**在于：

对正向迭代器进行 ++ 操作时，迭代器会指向容器中的后一个元素；而对反向迭代器进行 ++ 操作时，迭代器会指向容器中的前一个元素。

注意，以上 4 种定义迭代器的方式，并不是每个容器都适用。有一部分容器同时支持以上 4 种方式，比如 array、deque、vector；而有些容器只支持其中部分的定义方式，例如 forward_list 容器只支持定义正向迭代器，不支持定义反向迭代器。

具体容器支持定义迭代器的方式，讲具体容器时会详细说明。另外，读者也可以通过 C++ STL 标准手册，查询具体容器迭代器支持的定义方式。

## C++容器详解

> [C++ STL详解超全总结(快速入门STL)](https://blog.csdn.net/qq_50285142/article/details/114026148?ops_request_misc=%7B%22request%5Fid%22%3A%22166644512916782388029194%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=166644512916782388029194&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-114026148-null-null.142^v59^js_top,201^v3^control_2&utm_term=C%2B%2BSTL&spm=1018.2226.3001.4187)。

### C++容器分类

| 容器种类 | 功能                                                         |
| -------- | ------------------------------------------------------------ |
| 序列容器 | 主要包括 vector 向量容器、list 列表容器以及 deque 双端队列容器。 之所以被称为序列容器，是因为元素在容器中的位置同元素的值无关，即容器不是排序的。将元素插入容器时，指定在什么位置，元素就会位于什么位置。 |
| 排序容器 | 包括 set 集合容器、multiset 多重集合容器、map 映射容器以及 multimap 多重映射容器。 排序容器中的元素默认是由小到大排序好的，即便是插入元素，元素也会插入到适当位置。所以关联容器在查找时具有非常好的性能。 |
| 哈希容器 | C++ 11 新加入 4 种关联式容器，分别是 unordered_set 哈希集合、unordered_multiset 哈希多重集合、unordered_map 哈希映射以及 unordered_multimap 哈希多重映射。 和排序容器不同，哈希容器中的元素是未排序的，元素的位置由哈希函数确定。 |

| 容器类型                 | 介绍                                                         |
| ------------------------ | ------------------------------------------------------------ |
| 向量(vector)             | 连续存储的元素                                               |
| 列表(list)               | 由节点组成的双向链表，每个结点包含着一个元素                 |
| 双队列(deque)            | 连续存储的指向不同元素的指针所组成的数组                     |
| 集合(set)                | 由节点组成的红黑树，每个节点都包含着一个元素，节点之间以某种作用于元素对的谓词排列，没有两个不同的元素能够拥有相同的次序 |
| 多重集合(multiset)       | 允许存在两个次序相等的元素的集合                             |
| 栈(stack)                | 后进先出的值的排列                                           |
| 队列(queue)              | 先进先出的执的排列                                           |
| 优先队列(priority_queue) | 元素的次序是由作用于所存储的值对上的某种谓词决定的的一种队列 |
| 映射(map)                | 由{键，值}对组成的集合，以某种作用于键对上的谓词排列         |
| 多重映射(multimap)       | 允许键对有相等的次序的映射                                   |

### C++STL序列式容器

#### 数组容器（array）

> `array<T,N>` ：表示可以存储 N 个 T 类型的元素，是 **[C++](https://haicoder.net/cpp/cpp-tutorial.html)** 本身提供的一种容器。此类容器一旦建立，其长度就是固定不变的，这意味着不能增加或删除元素，只能改变某个元素的值。

##### 初始化

```c++
std::array<double, 10> values {};	//全部赋初值为0.0	
std::array<double, 10> values {0.1,1.4,1.8,,2.4};	//初始化4个元素，其余元素赋值为0
```

##### array成员函数

| 成员函数            | 功能                                                         |
| ------------------- | ------------------------------------------------------------ |
| begin()             | 返回指向容器中第一个元素的随机访问迭代器。                   |
| end()               | 返回指向容器最后一个元素之后一个位置的随机访问迭代器，通常和 begin() 结合使用。 |
| rbegin()            | 返回指向最后一个元素的随机访问迭代器。                       |
| rend()              | 返回指向第一个元素之前一个位置的随机访问迭代器。             |
| cbegin()            | 和 begin() 功能相同，只不过在其基础上增加了 const 属性，不能用于修改元素。 |
| cend()              | 和 end() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crbegin()           | 和 rbegin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crend()             | 和 rend() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| size()              | 返回容器中当前元素的数量，其值始终等于初始化 array 类的第二个模板参数 N。 |
| max_size()          | 返回容器可容纳元素的最大数量，其值始终等于初始化 array 类的第二个模板参数 N。 |
| empty()             | 判断容器是否为空，和通过 size()==0 的判断条件功能相同，但其效率可能更快。 |
| at(n)               | 返回容器中 n 位置处元素的引用，该函数自动检查 n 是否在有效的范围内，如果不是则抛出 out_of_range 异常。 |
| front()             | 返回容器中第一个元素的直接引用，该函数不适用于空的 array 容器。 |
| back()              | 返回容器中最后一个元素的直接应用，该函数同样不适用于空的 array 容器。 |
| data()              | 返回一个指向容器首个元素的指针。利用该指针，可实现复制容器中所有元素等类似功能。 |
| fill(val)           | 将 val 这个值赋值给容器中的每个元素。                        |
| array1.swap(array2) | 交换 array1 和 array2 容器中的所有元素，但前提是它们具有相同的长度和类型。 |

##### array迭代器

> 值得一提的是，以上函数在实际使用时，其返回值类型都可以使用 `auto` 关键字代替，编译器可以自行判断出该迭代器的类型。

###### begin和end迭代器

使用 begin 和 end 迭代器访问元素

```c++
#include <iostream>
#include <array>
using namespace std;
int main()
{
    array<int, 5> arr;
    int v = 1;
    auto first = arr.begin();
    auto last = arr.end();
    while (first != last)
    {
        *first = v;
        ++first;
        v++;
    }
    first = arr.begin();
    while (first != last)
    {
        cout << *first << " ";
        ++first;
    }
    cout << "\n";
    return 0; 
}
```

###### cbegin和cend迭代器

使用 cbegin 和 cend 迭代器访问元素

```c++
#include <iostream>
#include <array>
using namespace std;
int main()
{
    array<int, 5> arr{10, 20, 30, 40, 50};
    auto first = arr.cbegin();
    auto last = arr.cend();
    while (first != last)
    {
        cout << *first << " ";
        ++first;
    }
    cout << "\n";
    return 0; 
}
```

#### 向量容器（vector）

> `vector<T>`：用来存放 T 类型的元素，是一个长度可变的序列容器，即在存储空间不足时，会自动申请更多的内存。使用此容器，在尾部增加或删除元素的效率最高（时间复杂度为 O(1) 常数阶），在其它位置插入或删除元素效率较差（时间复杂度为 O(n) 线性阶，其中 n 为容器中元素的个数）。

[vector介绍与使用(C++)](https://blog.csdn.net/weixin_62029250/article/details/124124046?ops_request_misc=&request_id=&biz_id=102&utm_term=vector&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-4-124124046.nonecase&spm=1018.2226.3001.4187)

[C++ vector 实现二维数组](https://blog.csdn.net/a819825294/article/details/52088732)

vector 容器是 **[STL](https://haicoder.net/stl/stl-tutorial.html)** 中最常用的容器之一，它和 array 容器非常类似，都可以看做是对 **[C++](https://haicoder.net/cpp/cpp-tutorial.html)** 普通数组的 “升级版”。不同之处在于，array 实现的是静态数组（容量固定的数组），而 vector 实现的是一个动态数组，即可以进行元素的插入和删除，在此过程中，vector 会动态调整所占用的内存空间，整个过程无需人工干预。

vector 常被称为向量容器，因为该容器擅长在尾部插入或删除元素，在常量时间内就可以完成，时间复杂度为 O(1)；而对于在容器头部或者中部插入或删除元素，则花费时间要长一些（移动元素需要耗费时间），时间复杂度为线性阶 O(n)。

##### 初始化

```c++
std::vector<type> values {val1, val2, val3};	//赋初值
std::vector<type> values(size);		//指定容量
std::vector<type> value2(value1);	//用value1初始化value2
```

##### vector成员函数

| 函数成员         | 函数功能                                                     |
| ---------------- | ------------------------------------------------------------ |
| begin()          | 返回指向容器中第一个元素的迭代器。                           |
| end()            | 返回指向容器最后一个元素所在位置后一个位置的迭代器，通常和 begin() 结合使用。 |
| rbegin()         | 返回指向最后一个元素的迭代器。                               |
| rend()           | 返回指向第一个元素所在位置前一个位置的迭代器。               |
| cbegin()         | 和 begin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| cend()           | 和 end() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crbegin()        | 和 rbegin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crend()          | 和 rend() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| size()           | 返回实际元素个数。                                           |
| max_size()       | 返回元素个数的最大值。这通常是一个很大的值，一般是 232-1，所以我们很少会用到这个函数。 |
| resize()         | 改变实际元素的个数。                                         |
| capacity()       | 返回当前容量。                                               |
| empty()          | 判断容器中是否有元素，若无元素，则返回 true；反之，返回 false。 |
| reserve()        | 增加容器的容量。                                             |
| shrink _to_fit() | 将内存减少到等于当前元素实际所使用的大小。                   |
| operator[ ]      | 重载了 [ ] 运算符，可以向访问数组中元素那样，通过下标即可访问甚至修改 vector 容器中的元素。 |
| at()             | 使用经过边界检查的索引访问元素。                             |
| front()          | 返回第一个元素的引用。                                       |
| back()           | 返回最后一个元素的引用。                                     |
| data()           | 返回指向容器中第一个元素的指针。                             |
| assign()         | 用新元素替换原有内容。                                       |
| push_back()      | 在序列的尾部添加一个元素。                                   |
| pop_back()       | 移出序列尾部的元素。                                         |
| insert()         | 在指定的位置插入一个或多个元素。                             |
| erase()          | 移出一个元素或一段元素。                                     |
| clear()          | 移出所有的元素，容器大小变为 0。                             |
| swap()           | 交换两个容器的所有元素。                                     |
| emplace()        | 在指定的位置直接生成一个元素。                               |
| emplace_back()   | 在序列尾部生成一个元素。                                     |

##### vector迭代器

> 跟array的迭代器使用方法完全相同，不多说啦

##### vector扩容

> 空的vector不能使用迭代器

```c++
//利用reserve扩容
//可以看到扩容以后vector的首地址发生了变化
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<int> vec{1, 2, 3};
    cout << "Addr = " << vec.data() << endl;
    vec.reserve(5);
    cout << "Addr2 = " << vec.data() << endl;
    return 0; 
}
```

![22_C STL vector扩容.png](https://haicoder.net/uploads/pic/server/stl/stl-container/22_C++%20STL%20vector%E6%89%A9%E5%AE%B9.png)

##### vector插入元素

###### STL insert详解

| 语法格式                        | 用法说明                                                     |
| ------------------------------- | ------------------------------------------------------------ |
| iterator insert(pos,elem)       | 在迭代器 pos 指定的位置之前插入一个新元素elem，并返回表示新插入元素位置的迭代器。 |
| iterator insert(pos,n,elem)     | 在迭代器 pos 指定的位置之前插入 n 个元素 elem，并返回表示第一个新插入元素位置的迭代器。 |
| iterator insert(pos,first,last) | 在迭代器 pos 指定的位置之前，插入其他容器（不仅限于vector）中位于 [first,last) 区域的所有元素，并返回表示第一个新插入元素位置的迭代器。 |
| iterator insert(pos,initlist)   | 在迭代器 pos 指定的位置之前，插入初始化列表（用大括号{}括起来的多个元素，中间有逗号隔开）中所有的元素，并返回表示第一个新插入元素位置的迭代器。 |

```c++
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<int> vec{1, 5};
    vec.insert(vec.begin() + 1, 3);
    for (auto&& value : vec)
    {
		cout << value << " ";
	}
	cout << endl;
	vec.insert(vec.end(), 2, 50);
	for (auto&& value : vec)
    {
		cout << value << " ";
	}
	cout << endl;
    return 0; 
}
```

###### STL emplac详解

```c++
iterator emplace (const_iterator pos, args...);
```

| 参数    | 描述                                                         |
| ------- | ------------------------------------------------------------ |
| *pos*   | 需要插入的位置。                                             |
| *args…* | 表示与新插入元素的构造函数相对应的多个参数；该函数会返回表示新插入元素位置的迭代器。 |

```c++
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<int> vec{1, 5};
    vec.emplace(vec.begin(), 3);
    for (auto&& value : vec)
    {
		cout << value << " ";
	}
	cout << endl;
    return 0; 
}
```

##### vector添加元素

```c++
#include <iostream>
#include <vector>
using namespace std;
int main()
{
    vector<string> vec;	
    vec.push_back("HaiCoder");
    vec.emplace_bake("www.haicoder.net");
    for (auto&& value : vec)
    {
		cout << "Val = " << value << endl;
	}
    return 0; 
}
```

> **emplace_back()和push_back()的区别**

emplace_back() 和 push_back() 的区别，就在于底层实现的机制不同。push_back() 向容器尾部添加元素时，首先会创建这个元素，然后再将这个元素拷贝或者移动到容器中（如果是拷贝的话，事后会自行销毁先前创建的这个元素）；而 emplace_back() 在实现时，则是直接在容器尾部创建这个元素，省去了拷贝或移动元素的过程。

显然完成同样的操作，push_back() 的底层实现过程比 emplace_back() 更繁琐，换句话说，emplace_back() 的执行效率比 push_back() 高。因此，在实际使用时，建议大家优先选用 emplace_back()。

由于 emplace_back() 是 C++ 11 标准新增加的，如果程序要兼顾之前的版本，还是应该使用 push_back()。

##### vector删除元素

| 函数                  | 功能                                                         |
| --------------------- | ------------------------------------------------------------ |
| pop_back()            | 删除 vector 容器中最后一个元素，该容器的大小（size）会减 1，但容量（capacity）不会发生改变。 |
| erase(pos)            | 删除 vector 容器中 pos 迭代器指定位置处的元素，并返回指向被删除元素下一个位置元素的迭代器。该容器的大小（size）会减 1，但容量（capacity）不会发生改变。 |
| swap(beg)、pop_back() | 先调用 swap() 函数交换要删除的目标元素和容器最后一个元素的位置，然后使用 pop_back() 删除该目标元素。 |
| erase(beg,end)        | 删除 vector 容器中位于迭代器 [beg,end)指定区域内的所有元素，并返回指向被删除区域下一个位置元素的迭代器。该容器的大小（size）会减小，但容量（capacity）不会发生改变。 |
| remove()              | 删除容器中所有和指定元素值相等的元素，并返回指向最后一个元素下一个位置的迭代器。值得一提的是，调用该函数不会改变容器的大小和容量。 |
| clear()               | 删除 vector 容器中所有的元素，使其变成空的 vector 容器。该函数会改变 vector 的大小（变为 0），但不是改变其容量。 |

#### 双端队列容器（deque）

> `deque<T>`：和 vector 非常相似，区别在于使用该容器不仅尾部插入和删除元素高效，在头部插入或删除元素也同样高效，时间复杂度都是 O(1) 常数阶，但是在容器中某一位置处插入或删除元素，时间复杂度为 O(n) 线性阶。

##### deque成员函数

> 和 vector 相比，额外增加了实现在容器头部添加和删除元素的成员函数，同时删除了 capacity()、reserve() 和 data() 成员函数。

| 函数成员         | 函数功能                                                     |
| ---------------- | ------------------------------------------------------------ |
| begin()          | 返回指向容器中第一个元素的迭代器。                           |
| end()            | 返回指向容器最后一个元素所在位置后一个位置的迭代器，通常和 begin() 结合使用。 |
| rbegin()         | 返回指向最后一个元素的迭代器。                               |
| rend()           | 返回指向第一个元素所在位置前一个位置的迭代器。               |
| cbegin()         | 和 begin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| cend()           | 和 end() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crbegin()        | 和 rbegin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crend()          | 和 rend() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| size()           | 返回实际元素个数。                                           |
| max_size()       | 返回容器所能容纳元素个数的最大值。这通常是一个很大的值，一般是 232-1，我们很少会用到这个函数。 |
| resize()         | 改变实际元素的个数。                                         |
| empty()          | 判断容器中是否有元素，若无元素，则返回 true；反之，返回 false。 |
| shrink _to_fit() | 将内存减少到等于当前元素实际所使用的大小。                   |
| at()             | 使用经过边界检查的索引访问元素。                             |
| front()          | 返回第一个元素的引用。                                       |
| back()           | 返回最后一个元素的引用。                                     |
| assign()         | 用新元素替换原有内容。                                       |
| **push_back()**  | **在序列的尾部添加一个元素。**                               |
| **push_front()** | **在序列的头部添加一个元素。**                               |
| **pop_back()**   | **移除容器尾部的元素。**                                     |
| **pop_front()**  | **移除容器头部的元素。**                                     |
| insert()         | 在指定的位置插入一个或多个元素。                             |
| erase()          | 移除一个元素或一段元素。                                     |
| clear()          | 移出所有的元素，容器大小变为 0。                             |
| swap()           | 交换两个容器的所有元素。                                     |
| emplace()        | 在指定的位置直接生成一个元素。                               |
| emplace_front()  | 在容器头部生成一个元素。和 push_front() 的区别是，该函数直接在容器头部构造元素，省去了复制移动元素的过程。 |
| emplace_back()   | 在容器尾部生成一个元素。和 push_back() 的区别是，该函数直接在容器尾部构造元素，省去了复制移动元素的过程。 |

#### 链表容器（list）

> `list<T>`：是一个长度可变的、由 T 类型元素组成的序列，它以双向链表的形式组织元素，在这个序列的任何地方都可以高效地增加或删除元素（时间复杂度都为常数阶 O(1)），但访问容器中任意元素的速度要比前三种容器慢，这是因为 list 必须从第一个元素或最后一个元素开始访问，需要沿着链表移动，直到到达想要的元素。

##### list成员函数

| 成员函数         | 功能                                                         |
| ---------------- | ------------------------------------------------------------ |
| begin()          | 返回指向容器中第一个元素的双向迭代器。                       |
| end()            | 返回指向容器中最后一个元素的双向迭代器。                     |
| rbegin()         | 返回指向最后一个元素的反向双向迭代器。                       |
| rend()           | 返回指向第一个元素所在位置前一个位置的反向双向迭代器。       |
| cbegin()         | 和 begin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| cend()           | 和 end() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crbegin()        | 和 rbegin() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| crend()          | 和 rend() 功能相同，只不过在其基础上，增加了 const 属性，不能用于修改元素。 |
| empty()          | 判断容器中是否有元素，若无元素，则返回 true；反之，返回 false。 |
| size()           | 返回当前容器实际包含的元素个数。                             |
| max_size()       | 返回容器所能包含元素个数的最大值。这通常是一个很大的值，一般是 232-1，所以我们很少会用到这个函数。 |
| front()          | 返回第一个元素的引用。                                       |
| back()           | 返回最后一个元素的引用。                                     |
| assign()         | 用新元素替换容器中原有内容。                                 |
| emplace_front()  | 在容器头部生成一个元素。该函数和 push_front() 的功能相同，但效率更高。 |
| **push_front()** | **在容器头部插入一个元素。**                                 |
| **pop_front()**  | **删除容器头部的一个元素。**                                 |
| emplace_back()   | 在容器尾部直接生成一个元素。该函数和 push_back() 的功能相同，但效率更高。 |
| **push_back()**  | **在容器尾部插入一个元素。**                                 |
| **pop_back()**   | **删除容器尾部的一个元素。**                                 |
| emplace()        | 在容器中的指定位置插入元素。该函数和 insert() 功能相同，但效率更高。 |
| insert()         | 在容器中的指定位置插入元素。                                 |
| erase()          | 删除容器中一个或某区域内的元素。                             |
| swap()           | 交换两个容器中的元素，必须保证这两个容器中存储的元素类型是相同的。 |
| resize()         | 调整容器的大小。                                             |
| clear()          | 删除容器存储的所有元素。                                     |
| splice()         | 将一个 list 容器中的元素插入到另一个容器的指定位置。         |
| remove(val)      | 删除容器中所有等于 val 的元素。                              |
| remove_if()      | 删除容器中满足条件的元素。                                   |
| unique()         | 删除容器中相邻的重复元素，只保留一个。                       |
| merge()          | 合并两个事先已排好序的 list 容器，并且合并之后的 list 容器依然是有序的。 |
| sort()           | 通过更改容器中元素的位置，将它们进行排序。                   |
| reverse()        | 反转容器中元素的顺序。                                       |

##### list访问元素

> 只能访问首元素和尾元素

##### STL list insert详解

| 语法格式                        | 用法说明                                                     |
| ------------------------------- | ------------------------------------------------------------ |
| iterator insert(pos,elem)       | 在迭代器 pos 指定的位置之前插入一个新元素 elem，并返回表示新插入元素位置的迭代器。 |
| iterator insert(pos,n,elem)     | 在迭代器 pos 指定的位置之前插入 n 个元素 elem，并返回表示第一个新插入元素位置的迭代器。 |
| iterator insert(pos,first,last) | 在迭代器 pos 指定的位置之前，插入其他容器（例如 array、vector、deque 等）中位于 [first,last) 区域的所有元素，并返回表示第一个新插入元素位置的迭代器。 |
| iterator insert(pos,initlist)   | 在迭代器 pos 指定的位置之前，插入初始化列表（用大括号 { } 括起来的多个元素，中间有逗号隔开）中所有的元素，并返回表示第一个新插入元素位置的迭代器。 |

```c++
#include <iostream>
#include <list>
using namespace std;
int main()
{
    list<int> vec{1, 5};
    vec.insert(vec.begin(), 3);
    for (auto&& value : vec)
    {
		cout << value << " ";
	}
	cout << endl;
	vec.insert(vec.end(), 2, 50);
	for (auto&& value : vec)
    {
		cout << value << " ";
	}
	cout << endl;
    return 0; 
}
```

![70_C STL list插入元素.png](https://haicoder.net/uploads/pic/server/stl/stl-container/70_C++%20STL%20list%E6%8F%92%E5%85%A5%E5%85%83%E7%B4%A0.png)

##### STL list splice详解

> 和 insert() 成员方法相比，splice() 成员方法的作用对象是其它 list 容器，其功能是将其它 list 容器中的元素添加到当前 list 容器中指定位置处。

我们知道，list 容器底层使用的是链表存储结构，splice() 成员方法**移动**元素的方式是，将存储该元素的节点从 list 容器底层的链表中摘除，然后再链接到当前 list 容器底层的链表中。

这意味着，当使用 splice() 成员方法将 x 容器中的元素添加到当前容器的同时，**该元素会从 x 容器中删除**。

| 语法格式                                                     | 功能                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| void splice (iterator position, list& x);                    | position 为迭代器，用于指明插入位置；x 为另一个 list 容器。 此格式的 splice() 方法的功能是，将 x 容器中存储的所有元素全部移动当前 list 容器中 position 指明的位置处。 |
| void splice (iterator position, list& x, iterator i);        | position 为迭代器，用于指明插入位置；x 为另一个 list 容器；i 也是一个迭代器，用于指向 x 容器中某个元素。 此格式的 splice() 方法的功能是将 x 容器中 i 指向的元素移动到当前容器中 position 指明的位置处。 |
| void splice (iterator position, list& x, iterator first, iterator last); | position 为迭代器，用于指明插入位置；x 为另一个 list 容器；first 和 last 都是迭代器，[fist,last) 用于指定 x 容器中的某个区域。 此格式的 splice() 方法的功能是将 x 容器 [first, last) 范围内所有的元素移动到当前容器 position 指明的位置处。 |

```c++
#include <iostream>
#include <list>
using namespace std;
int main()
{
    list<int> list1{1, 2, 3, 4}, list2{10, 20, 30};
    list<int>::iterator it = ++list1.begin();
    list1.splice(it, list2);
    for (auto iter = list1.begin(); iter != list1.end(); ++iter) {
        cout << *iter << " ";
    }
    cout << endl;
    list2.splice(list2.begin(), list1, it);    
    for (auto iter = list2.begin(); iter != list2.end(); ++iter) {
        cout << *iter << " ";
    }
    cout << endl;
    return 0; 
}
```

![72_C STL list插入元素.png](https://haicoder.net/uploads/pic/server/stl/stl-container/72_C++%20STL%20list%E6%8F%92%E5%85%A5%E5%85%83%E7%B4%A0.png)

##### list删除元素

| 成员函数    | 功能                                                         |
| ----------- | ------------------------------------------------------------ |
| pop_front() | 删除位于 list 容器头部的一个元素。                           |
| pop_back()  | 删除位于 list 容器尾部的一个元素。                           |
| erase()     | 该成员函数既可以删除 list 容器中指定位置处的元素，也可以删除容器中某个区域内的多个元素。 |
| clear()     | 删除 list 容器存储的所有元素。                               |
| remove(val) | 删除容器中所有等于 val 的元素。                              |
| unique()    | 删除容器中相邻的重复元素，只保留一份。                       |
| remove_if() | 删除容器中满足条件的元素。                                   |

#### 正向链表容器（forward_list）

> `forward_list<T>`：和 list 容器非常类似，只不过它以单链表的形式组织元素，它内部的元素只能从第一个元素开始访问，是一类比链表容器快、更节省内存的容器。

几乎同上，不多解释

### C++STL关联式容器

### C++STL无序关联式容器



#### [map（映射）](https://blog.csdn.net/qq_50285142/article/details/120368977)



### [String（字符串）](https://blog.csdn.net/qq_50285142/article/details/114156051)

#### 字符串操作函数

###### `str.assign()`

> 字符串的赋值

###### `str.size()` 和 `str.length()`

> 字符串长度

###### `s.empty()`

> 字符串判空

###### `str1 + str2` 和 `str1 += str2`

> 字符串拼接

###### `str1 == str2` 和 `str1 != str2`

> 判定字符串是否相等，不是判断地址

###### `str.push_back()`

> 在字符串末尾插入字符

###### `str.insert()`

> 该函数有10种不同的重载

| 序号 | 功能                                                         |
| :--: | :----------------------------------------------------------- |
|  1   | 在 index 位置插入 count 个字符 ch                            |
|  2   | index 位置插入一个常量字符串                                 |
|  3   | index 位置插入常量字符串中的 count 个字符                    |
|  4   | index 位置插入常量 string                                    |
|  5   | index 位置插入常量 str 的从 index_str 开始的 count 个字符    |
|  6   | index 位置插入常量 str 从 index_str 开始的 count 个字符，count 可以表示的最大值为 npos。 |
|  7   | 在 pos 位置处插入字符 ch                                     |
|  8   | 迭代器指向的 pos 位置插入 count 个字符 ch                    |
|  9   | 迭代器指向的 pos 位置插入 count 个字符 ch                    |
|  10  | 迭代器指向的 pos 位置插入一段字符串                          |

```c++
1. basic_string& insert( size_type index, size_type count, CharT ch );
2. basic_string& insert( size_type index, const CharT* s );
3. basic_string& insert( size_type index, const CharT* s, size_type count );
4. basic_string& insert( size_type index, const basic_string& str );
5. basic_string& insert( size_type index, const basic_string& str, size_type index_str, size_type count );
6. basic_string& insert( size_type index, const basic_string& str, size_type index_str, size_type count = npos);
7.      iterator insert( iterator pos, CharT ch );
        iterator insert( const_iterator pos, CharT ch );
8. 			void insert( iterator pos, size_type count, CharT ch );
9. 		iterator insert( const_iterator pos, size_type count, CharT ch );
10. 		void insert( iterator pos, InputIt first, InputIt last );
    	iterator insert( const_iterator pos, InputIt first, InputIt last );
```

###### `str.append()`

> 字符串追加子串

```c++
	string s1 = "Hello";
    string s2 = " HaiCoder";
    s1.append(s2, 1, 2);
    cout << "append s1 = " << s1 << endl;
	s1.append(3, 'H');
    cout << "append s1 = " << s1 << endl;
	s1.append("ABCDE", 2, 3);
    cout << "append s1 = " << s1 << endl;

```

<img src="https://haicoder.net/uploads/pic/server/cpp/cpp-string/09_C++%E5%AD%97%E7%AC%A6%E4%B8%B2string%E8%BF%BD%E5%8A%A0append.png"  />

###### `str.compare()`

> 字符串比较

```c++
int n = s1.compare(s2);
n = s1.compare(1, 2, s2, 0, 3);  //比较s1的子串 (1,2) 和s2的子串 (0,3)
n = s1.compare(0, 2, s2);  // 比较s1的子串 (0,2) 和 s2
n = s1.compare("Hello");
n = s1.compare(1, 2, "Hello");  //比较 s1 的子串(1,2)和"Hello”
n = s1.compare(1, 2, "Hello", 1, 2);  //比较 s1 的子串(1,2)和 "Hello" 的子串(1,2)
//如果返回值小于 0 表示当前的字符串小；等于 0 表示两个字符串相等；大于 0 表示另一个字符串小。
```

###### `str.substr()`

> 截取字符串

```c++
string substr(int pos = 0, int n = string::npos) const;

//例子
string str = "Hello HaiCoder";
	string retStr = str.substr(6, 3);
	cout << "Str = " << str << ", RetStr = " << retStr << endl;
```

![](https://haicoder.net/uploads/pic/server/cpp/cpp-string/17_C++%E5%AD%97%E7%AC%A6%E4%B8%B2string%E6%88%AA%E5%8F%96substr.png)

###### `str1.swap(str2)`

> 交换字符串

###### `str.find()`	

> 字符串查找

```c++
int n = s1.find(s2);
```

###### `str.rfind()`

> 反向查找，查找的起始位置是反的，但是查找的字符串序列是正序的

###### `str.find_first_of(str2)`

> 查找子串**任意**字符在字符串出现的第一个位置

```c++
	string str1 = "I love HaiCoder and i learn C++ from HaiCoder";
    int findIndex1 = str1.find_first_of("evol");
    int findIndex2 = str1.find_first_of("AO");
	cout << "findIndex1 = " << findIndex1 << ", findIndex2 = " << findIndex2 << endl;
```

![24_C find_first_of.png](https://haicoder.net/uploads/pic/server/cpp/cpp-string/24_C++%20find_first_of.png)

###### `str.find_last_of(str2)`

> 查找子串**任意**字符在字符串出现的最后一个位置

###### `str.find_first_not_of(s2)`

> 返回第一个不在子串s2中的字符的索引

###### `str.find_last_not_of(s2)`

> 返回最后一个不在子串s2中的字符的索引

###### `str.replace()`

> 字符串替换

```c++
	string str1 = "I love HaiCoder and i learn C++ from HaiCoder";
 	string newStr = str1.replace(2, 4, "LIKE");	//从位置2开始的4个字符
  	string newStr = str1.replace(str1.begin(), str1.begin()+6, "LIKE");	//利用迭代器，首位置开始的6个字符
	string newStr = str1.replace(0, 5, substr, substr.find("2"), 3);	//替换指定位置的字符串
```

###### `str.clear()`

> 清空字符串

###### `str.erase()`

> 删除子串

```c++
str.erase(iterator p);		//删除迭代器指向的字符
str.erase(iterator first, iterator last);	//删除两个迭代器之间的子串
str.erase(pos, len);	//删除pos到len之间的子串
```

> 如果需要保留pos1到pos2之间的字符，除了用`str.substr()`以外，还可以删掉需保留字符串前后的字符串：

```c++
#include <string>
int main(){
    string = str;
    str.erase(0,pos1);
	str.erase(pos2,str.max_size());
    return 0；
}
```

###### `reverse(str.begin(), str.end())`

> 字符串翻转；需要引入头文件`<algorithm>`

```c++
#include <algorithm>
using namespace std;
int main()
{
	string str = "Hello HaiCoder";
	cout << "Origin str = " << str << endl;
	reverse(str.begin()+6, str.end());
	cout << "New str = " << str << endl;
	return 0;
}
```

![](https://haicoder.net/uploads/pic/server/cpp/cpp-string/36_C++%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%8F%8D%E8%BD%ACreverse.png)

###### `tolower(str[i])` 和 `toupper(str[i])`

> 大小写转换

```c++
//通过stl的transform算法配合tolower 和 toupper 实现。
//有4个参数，前2个指定要转换的容器的起止范围，第3个参数是结果存放容器的起始位置，第4个参数是一元运算。
string s;
transform(s.begin(),s.end(),s.begin(),::tolower);//转换小写
transform(s.begin(),s.end(),s.begin(),::toupper);//转换大写
```

###### `str.c_str()`

> string向char数组转换

```c++
string s = "xing ma qi";
char s2[] = s.c_str();
```

###### `sort()`

```c++
#include <string>
sort(str.begin(), str.end(), cmp);
//cmp可以是自己定义的以bool为返回值的函数
//也可以是默认的升序（less<string>()），或者降序（greater<string>()）（该演示为字典序，<>中可以填整型或者其它数据类型）

//二维数组排序示例
sort(str.begin(), str.end(), [](vector<int>&a, vector<int>&b){return a[1] > b[1]});
```

#### [c++读取字符串和字符的函数](https://blog.csdn.net/weixin_51216553/article/details/120005801?ops_request_misc=%7B%22request%5Fid%22%3A%22166667029116800182141654%22%2C%22scm%22%3A%2220140713.130102334.pc%5Fall.%22%7D&request_id=166667029116800182141654&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v1~rank_v31_ecpm-5-120005801-null-null.142^v59^pc_rank_34_queryrelevant25,201^v3^control_1&utm_term=c%2B%2B读取字符串&spm=1018.2226.3001.4187).

###### `scanf`

> 用于字符串数组，遇到空格或者换行符停止

###### `getline()`

> 可以接受空格，遇到换行符停止
>
> 两种读取方法，法一是string流，法二是iostream流，是两个不一样的函数

- 使用string

  ```c++
  string str;
  getline(cin, str);
  cout<<str<<endl;
  ```

- 使用char数组

  ```c++
  char str[100];
  cin.getline(str, 20, '\n')
  //cin.getline()里面三个参数，第一个是要储存的字符串数组，第二个是最大长度 + 1，最后一个位置用来存储'\0'，也就是说你填20，但是只能存前19个字符，第三个是结束符，可省略，默认是换行符
  ```

###### `get()`

> `get()`不会读取并且丢弃换行符，而是会将其保留在队列中
>
>  第二次调用`get()`时，容易读取到上次没读取的换行符，而不读取任何内容。

###### `gets()`

>gets和getline一样，不会将结束符或换行符留在缓冲区，不过如果缓冲区有结束符或换行符，他也会读进去，所以在前面要加个`getchar()`

###### `getchar()`

>从缓冲区读走一个字符，如果输入多个字符，它也只会读取第一个

#### 字符串的转换函数

> [字符串和整型之间的相互转换](https://blog.csdn.net/weixin_52340203/article/details/114440766?ops_request_misc=%7B%22request%5Fid%22%3A%22166676583716782414998601%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=166676583716782414998601&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~baidu_landing_v2~default-1-114440766-null-null.142^v59^pc_rank_34_queryrelevant25,201^v3^control_1,213^v1^control&utm_term=字符串和整型的转换&spm=1018.2226.3001.4187).

###### `sscanf(str, "%d", &a)`

> 从字符串读取整型

###### `sprintf(str, "%d", a)`

> 将整型输出到字符串中

###### `to_string()`

> 可以将整数型，浮点型转换为字符串`string`类型

###### [`atoi()`](https://blog.csdn.net/weixin_54792212/article/details/123184537?ops_request_misc=&request_id=&biz_id=102&utm_term=atoi&utm_medium=distribute.pc_search_result.none-task-blog-2~all~sobaiduweb~default-0-123184537.142^v59^pc_rank_34_queryrelevant25,201^v3^control_1&spm=1018.2226.3001.4187) 和 `stoi()`

> `atoi`只能对char数组进行操作；`stoi()`可以直接对string进行操作

```c++
int atoi(const char *str)
int stoi(const string *str)
```

###### `atol()` 

> `atol()`将char数组转换为长整型；`atof()`将char数组转换为`double`类型

```c++
long atol(const char *str);
```

###### `atof()`

> 详细解释：`atof()`会扫描参数nptr字符串，跳过前面的空格字符，直到遇上数字或正负符号才开始做转换，而再遇到非数字或字符串结束时 (’\0’)才结束转换，并将结果返回。参数nptr字符串可包含正负号、小数点或E(e)来表示指数部分，如123.456或123e-2。

```c++
double atof(const char *nptr);
```

###### [`itoa()`](https://blog.csdn.net/lanzhihui_10086/article/details/39960027?ops_request_misc=%7B%22request%5Fid%22%3A%22166676625816782395377677%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=166676625816782395377677&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~top_positive~default-1-39960027-null-null.142^v59^pc_rank_34_queryrelevant25,201^v3^control_1,213^v1^control&utm_term=itoa&spm=1018.2226.3001.4187)

> 将整数类型转换为char数组

```c++
//第一个参数是要转换的整型，第二个参数是char数组的地址，第三个参数是转换后的进制
char *itoa(int value, char *string, int radix);
```



