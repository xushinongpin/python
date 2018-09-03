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


