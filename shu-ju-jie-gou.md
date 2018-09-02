## 更多关于列表

列表数据类型有更多方法。以下是列表对象的所有方法：

```
list.append(x)
将项添加到列表的末尾。相当于 a[len(a):] = [x].

list.extend(iterable)
通过附加iterable中的所有项来扩展列表。相当于 a[len(a):] = iterable.

list.insert(i, x)
在给定位置插入项目。第一个参数是要插入的元素的索引, 因此 a.insert(0, x) 插入列表的前面，  a.insert(len(a), x) 等效于 a.append(x).

list.remove(x)
从列表中删除值等于x的第一个项目。ValueError如果没有这样的项目，它会引发一个 。

list.pop([i])
删除列表中给定位置的项目，然后将其返回。如果未指定索引，则a.pop()删除并返回列表中的最后一项。（方法签名中i周围的方括号表示该参数是可选的，而不是您应该在该位置键入方括号。您将在Python Library Reference中经常看到这种表示法。）

list.clear()
从列表中删除所有项目。相当于 del a[:].

list.index(x[, start[, end]])
在值等于x的第一个项的列表中返回从零开始的索引。ValueError如果没有这样的项目，则提高a

可选参数start和end被解释为切片表示法，并用于将搜索限制为列表的特定子序列。返回的索引是相对于完整序列的开头而不是start参数计算的。

list.count(x)
返回x出现在列表中的次数。

list.sort(key=None, reverse=False)
对列表中的项目进行排序（参数可用于排序自定义，请参阅sorted()其说明）。

list.reverse()
反转列表中的元素。

list.copy()
返回列表的浅表副本。相当于 a[:].
```

使用大多数列表方法的示例：

```
>>> fruits = ['orange','apple','peat','banana','kiwi','apple','banana']
>>> fruits.count('apple')
2
>>> fruits.count('tangerine')
0
>>> fruits.index('banana')
3
>>> fruits.index('banana',4)
6
>>> fruits.reverse()
>>> fruits
['banana', 'apple', 'kiwi', 'banana', 'peat', 'apple', 'orange']
>>> fruits.sort()
>>> fruits
['apple', 'apple', 'banana', 'banana', 'kiwi', 'orange', 'peat']
>>> fruits.pop()
'peat'
>>> fruits
['apple', 'apple', 'banana', 'banana', 'kiwi', 'orange']
>>>
```

注意：方法一样insert，remove或者sort只修改列表没有返回值印刷-它们返回的默认 None。 这是Python中所有可变数据结构的设计原则。

### 

### 

### 嵌套列表理解

列表推导中的初始表达式可以是任意表达式，包括另一个列表推导。

考虑以下3x4矩阵的示例，该矩阵实现为3个长度为4的列表的列表：

```
>>> matrix = [
...      [1,2,3,4],
...      [5,6,7,8],
...      [9,10,11,12],
... ]
>>> [[row[i] for row in matrix] for i in range(4)]
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
>>> # 等效
>>> transposed = []
>>> for i in range(4):
...     transposed.append([row[i] for row in matrix])
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
>>>

反之亦然：
>>> transposed = []
>>> for i in range(4):
...     # the following 3 lines implement the nested listcomp
...     transposed_row = []
...     for row in matrix:
...             transposed_row.append(row[i])
...     transposed.append(transposed_row)
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
>>>
```

## [`del`](https://docs.python.org/3/reference/simple_stmts.html#del)声明

有一种方法可以从列表中删除一个项目，而不是它的值：del语句。这与pop\(\)返回值的方法不同。该del语句还可用于从列表中删除切片或清除整个列表（我们之前通过将空列表分配给切片来执行此操作）。例如：

```
>>> a= [-1,1,66.25,333,333,1234.5]
>>> del a[0]
>>> a
[1, 66.25, 333, 333, 1234.5]
>>> del a[2:4]
>>> a
[1, 66.25, 1234.5]
>>> del a[:]
>>> a
[]
>>>  #del 也可以用来删除整个变量：
>>> del a
>>> a
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'a' is not defined
>>>
```

a以下引用名称是一个错误（至少在为其分配了另一个值之前）。我们会在del以后找到其他用途。

## 元组和序列

我们看到列表和字符串有许多常见属性，例如索引和切片操作。它们是_序列_数据类型的两个示例（请参阅[序列类型 - 列表，元组，范围](https://docs.python.org/3/library/stdtypes.html#typesseq)）。由于Python是一种不断发展的语言，因此可能会添加其他序列数据类型。还有另一种标准序列数据类型：_元组_。

元组由逗号分隔的多个值组成，例如：

```
>>> t = 12345,54321,'hello!'
>>> t[0]
12345
>>> t
(12345, 54321, 'hello!')
>>> # tuples may be nested:
... u = t, (1,2,3,4,5)
>>> u
((12345, 54321, 'hello!'), (1, 2, 3, 4, 5))
>>> # tuples are immutable:
... t[0] = 88888
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
TypeError: 'tuple' object does not support item assignment
>>> # but they can contain mutable objects:
... v = ([1,2,3],[3,2,1])
>>> v
([1, 2, 3], [3, 2, 1])
>>>
```

如您所见，输出元组始终用括号括起来，以便正确解释嵌套元组;它们可以输入有或没有周围的括号，尽管通常括号是必要的（如果元组是较大表达式的一部分）。无法分配元组的各个项，但是可以创建包含可变对象的元组，例如列表。

尽管元组看起来与列表类似，但它们通常用于不同的情况并用于不同的目的。元组是[不可变的](https://docs.python.org/3/glossary.html#term-immutable)，并且通常包含异构的元素序列，这些元素可以通过解包（参见本节后面部分）或索引（或者甚至是属性的情况下[`namedtuples`](https://docs.python.org/3/library/collections.html#collections.namedtuple)）来访问。列表是[可变的](https://docs.python.org/3/glossary.html#term-mutable)，它们的元素通常是同类的，可以通过遍历列表来访问。

一个特殊的问题是构造包含0或1项的元组：语法有一些额外的怪癖来适应这些。空元组是由一对空括号构成的;通过使用逗号跟随值来构造具有一个项目的元组（在括号中包含单个值是不够的）。丑陋但有效。例如：

```
>>> empty = ()
>>> singleton = 'hello',
>>> len(empty)
0
>>> len(singleton)
1
>>> singleton
('hello',)
>>>
```

## Sets

Python还包括_集合_的数据类型。集合是无序集合，没有重复元素。基本用途包括成员资格测试和消除重复条目。集合对象还支持数学运算，如并集，交集，差异和对称差异。

大括号或[`set()`](https://docs.python.org/3/library/stdtypes.html#set)函数可用于创建集合。注意：要创建一个空集，你必须使用`set()`，而不是`{}`;后者创建一个空字典，一个我们将在下一节讨论的数据结构。

这是一个简短的演示：

```
>>> basket = {'apple','orange','apple','pear','orange','banana'}
>>> print(basket)
{'orange', 'pear', 'apple', 'banana'}
>>> 'orange' in basket
True
>>> 'crabgrass' in basket
False
>>>
>>>
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a
{'a', 'd', 'c', 'r', 'b'}
>>> a - b
{'d', 'b', 'r'}
>>> a | b
{'a', 'd', 'z', 'm', 'c', 'r', 'b', 'l'}
>>> a & b
{'a', 'c'}
>>> a ^ b
{'m', 'b', 'r', 'd', 'z', 'l'}
>>>
```

与[列表推导](https://docs.python.org/3/tutorial/datastructures.html#tut-listcomps)类似，也支持集合理解：

```
>>> a = {x for x in 'abracadabra' if x not in 'abc'}
>>> a
{'d', 'r'}
>>>
```

## 字典

Python内置的另一个有用的数据类型是_字典_（请参阅[映射类型 - 字典](https://docs.python.org/3/library/stdtypes.html#typesmapping)）。词典有时在其他语言中被称为“关联记忆”或“关联阵列”。与通过一系列数字索引的序列不同，字典由_键_索引，_键_可以是任何不可变类型;字符串和数字总是键。如果元组仅包含字符串，数字或元组，则它们可用作键;如果元组直接或间接包含任何可变对象，则不能将其用作键。你不能用链表做关键字，因为链表可以用索引赋值，切片赋值，或类似的方法进行修改`append()`和`extend()`。

最好将字典视为一组_键：值_对，并要求键是唯一的（在一个字典中）。一对大括号创建一个空字典：`{}`。在括号内放置以逗号分隔的键：值对列表，将初始键：值对添加到字典中;这也是字典在输出上的写法。

字典上的主要操作是使用某个键存储值并提取给定键的值。也可以删除键：值对`del`。如果使用已在使用的密钥进行存储，则会忘记与该密钥关联的旧值。使用不存在的密钥提取值是错误的。

`list(d)`在字典上执行会按照插入顺序返回字典中使用的所有键的列表（如果您希望对其进行排序，则只需使用它`sorted(d)`）。要检查单个键是否在字典中，请使用[`in`](https://docs.python.org/3/reference/expressions.html#in)关键字。

这是一个使用字典的小例子：

```
>>> tel = {'jack':4098, 'sape': 4139}
>>> tel['guido'] = 4127
>>> tel
{'jack': 4098, 'sape': 4139, 'guido': 4127}
>>> tel['jack']
4098
>>> del tel['sape']
>>> tel['irv'] = 4127
>>> tel
{'jack': 4098, 'guido': 4127, 'irv': 4127}
>>> list(tel)
['jack', 'guido', 'irv']
>>> sorted(tel)
['guido', 'irv', 'jack']
>>> 'guido' in tel
True
>>> 'jack' not in tel
False
>>>
```

dict ： 构造直接从键-值对的序列构建字典

```
>>> dict([('sape',4139),('guido',4127),('jack',4098)])
{'sape': 4139, 'guido': 4127, 'jack': 4098}
```

dict comprehensions可用于从任意键和值表达式创建字典：

```
>>> {x: x**2 for x in (2,4,6)}
{2: 4, 4: 16, 6: 36}
```

当键是简单字符串时，有时使用关键字参数指定对更容易：

```
>>> dict(sape=4139,guido=4127,jack=4098)
{'sape': 4139, 'guido': 4127, 'jack': 4098}
>>>
```

## 循环技术

循环遍历字典时，可以使用该items\(\)方法同时检索密钥和相应的值。

```
>>> knights = {'gallahad':'the pure','robin':'the brave'}
>>> for k,v in knights.items():
...     print(k,v)
...
gallahad the pure
robin the brave
>>>
```

循环遍历序列时，可以使用该enumerate\(\)函数同时检索位置索引和相应的值。

```
>>> for i, v in enumerate(['tic','tac','toe']):
...     print(i, v)
...
0 tic
1 tac
2 toe
>>>
```

要同时循环两个或更多个序列，条目可以与该zip\(\)功能配对。

```
>>> questions = [' name','quest','favorite color']
>>> answers = ['lancelot','the holy grail','blue']
>>> for q, a in zip(questions, answers):
...     print('What is your {0}? It is {1}.'.format(q, a))
...
What is your  name? It is lancelot.
What is your quest? It is the holy grail.
What is your favorite color? It is blue.
```



