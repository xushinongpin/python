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



