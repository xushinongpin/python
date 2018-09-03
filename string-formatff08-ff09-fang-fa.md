### String format（）方法

str.format\(\)方法的基本用法如下所示：

```
>>> print('We are the {} eho say "{}!"'.format('knights','Ni'))
We are the knights eho say "Ni!"
>>>
```

其中的括号和字符（称为格式字段）将替换为传递给str.format\(\)方法的对象。括号中的数字可用于表示传递给str.format\(\)方法的对象的位置 。

```
>>> print(' {0} and {1}'.format('spam','eggs'))
 spam and eggs
>>> print(' {1} and {0}'.format('spam','eggs'))
 eggs and spam
>>>
```

如果在str.format\(\)方法中使用关键字参数，则使用参数的名称引用它们的值。

```
>>> print('This {food} is {abjective}.'.format(
...     food='spam', abjective='abjective horrible'))
This spam is abjective horrible.
>>>
```

位置和关键字参数可以任意组合：

```
>>> print('The story of {0}, {1}, and {order}.'.format('Bill','Manfred',
...     order='Georg'))
The story of Bill, Manfred, and Georg.
>>>
```

如果你有一个非常长的格式字符串，你不想拆分，那么如果你可以引用变量来按名称而不是按位置进行格式化将会很好。这可以通过简单地传递dict并使用方括号'\[\]'来访问键来完成

```
>>> table = {'Sjoerd': 4127, 'Jack': 4098, 'Dcab': 8637678}
>>> print('Jack: {0[Jack]:d}; Sjoerd: {0[Sjoerd]:d}; '
...     'Dcab: {0[Dcab]:d}'.format(table))
Jack: 4098; Sjoerd: 4127; Dcab: 8637678
>>>

这也可以通过将表作为关键字参数传递'**'表示法来完成。
>>> print('Jack: {Jack:d}; Sjoerd: {Sjoerd:d}; Dcab: {Dcab:d}'.format(**table))
Jack: 4098; Sjoerd: 4127; Dcab: 8637678
>>>
```

这与内置函数结合使用特别有用，内置函数 vars\(\)返回包含所有局部变量的字典。

例如，以下行生成一组整齐对齐的列，给出整数及其正方形和立方体：

```
>>> for x in range(1, 11):
...     print(' {0:2d} {1:3d} {2:4d}'.format(x,x*x,x*x*x))
...
  1   1    1
  2   4    8
  3   9   27
  4  16   64
  5  25  125
  6  36  216
  7  49  343
  8  64  512
  9  81  729
 10 100 1000
```

有关字符串格式的完整概述[`str.format()`](https://docs.python.org/3/library/stdtypes.html#str.format)，请参阅[格式字符串语法](https://docs.python.org/3/library/string.html#formatstrings)。

