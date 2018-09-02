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



