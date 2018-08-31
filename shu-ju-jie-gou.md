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

### 使用列表作为堆栈

list方法可以很容易地将列表用作堆栈，其中添加的最后一个元素是检索到的第一个元素（“last-in，first-out”）。要将项添加到堆栈顶部，请使用append\(\)。要从堆栈顶部检索项目，请在pop\(\)没有显式索引的情况下使用。例如：

```
>>> stack = [3,4,5]
>>> stack.append(6)
>>> stack.append(7)
>>> stack
[3, 4, 5, 6, 7]
>>> stack.pop()
7
>>> stack
[3, 4, 5, 6]
>>> stack.pop()
6
>>> stack.pop()
5
>>> stack
[3, 4]
>>>
```

### 使用列表作为队列

也可以使用列表作为队列，其中添加的第一个元素是检索的第一个元素（“先进先出”）; 但是，列表不能用于此目的。虽然列表末尾的追加和弹出很快，但是从列表的开头进行插入或弹出是很慢的（因为所有其他元素都必须移动一个）。

要实现队列，请使用[collections.deque](https://docs.python.org/3/library/collections.html#collections.deque)设计为具有快速追加和从两端弹出的队列。例如：

```
>>> from collections import deque
>>> queue = deque(["Eric","John","Michael"])
>>> queue.append("Terry")
>>> queue.append("Graham")
>>> queue.popleft()
'Eric'
>>> queue.popleft()
'John'
>>> queue
deque(['Michael', 'Terry', 'Graham'])
>>>
```

### 列表理解

列表推导提供了创建列表的简明方法。常见的应用是创建新的列表，其中每个元素是应用于另一个序列的每个成员或可迭代的一些操作的结果，或者创建满足特定条件的那些元素的子序列。

例如，假设我们要创建一个平方列表，例如：

```
>>> squares = []
>>> for x in range(10):
...     squares.append(x**2)
...
>>> squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
>>>
```

请注意，这会创建（或覆盖）一个名为x在循环完成后仍然存在的变量。我们可以使用以下方法计算没有任何副作用的正方形列表：

```
>>> squares = list(map(lambda x: x**2, range(20)))
>>> squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196, 225, 256, 289, 324, 361]
或者，等效地：
>>> squares = [x**2 for x in range(15)]
>>> squares
[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100, 121, 144, 169, 196]
>>>
```

这更简洁，更易读。

列表推导由括号组成，括号中包含一个表达式，后跟一个for子句，然后是零个或多个for或if 子句。结果将是一个新的列表，该列表是通过在其后面的for和if子句的上下文中评估表达式而得到的。例如，如果列表不相等，则此listcomp将两个列表的元素组合在一起：

```
>>> [(x,y) for x in [1,2,3] for y in [3,1,4] if x != y]
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)]
相当于：
>>> combs = []
>>> for x in [1,2,3]:
...     for y in [3,1,4]:
...             if x != y:
...                     combs.append((x,y))
...
>>> combs
[(1, 3), (1, 4), (2, 3), (2, 1), (2, 4), (3, 1), (3, 4)]
>>>
```

请注意这两个片段中for和if语句的顺序是如何相同的。

如果表达式是元组（例如前面示例中的元组），则必须将其括起来。\(x, y\)

```
>>> vec = [-4,-2,0,2,4]
>>> [x*2 for x in vec]
[-8, -4, 0, 4, 8]
>>> [x for x in vec if x >= 0]
[0, 2, 4]
>>> [abs(x) for x in vec]
[4, 2, 0, 2, 4]
>>> freshfruit = [' banana',' loganberry ','passion fruit ']
>>> [weapon.strip() for weapon in freshfruit]
['banana', 'loganberry', 'passion fruit']
>>> [(x,x**2) for x in range(6)]
[(0, 0), (1, 1), (2, 4), (3, 9), (4, 16), (5, 25)]
>>> ＃元组必须加括号，否则会引发错误
>>> [x,x**2 for x in range(6)]
  File "<stdin>", line 1
    [x,x**2 for x in range(6)]
              ^
SyntaxError: invalid syntax
>>> vec = [[1,2,3],[4,5,6],[7,8,9]]
>>> [num for elem in vec for num in elem]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
>>>
```

列表推导可以包含复杂的表达式和嵌套函数：

```
>>> from math import pi
>>> [str(round(pi,i)) for i in range(1,6)]
['3.1', '3.14', '3.142', '3.1416', '3.14159']
>>>
```

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



