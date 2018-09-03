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



