### 格式化字符串文字

[格式化的字符串文字](https://docs.python.org/3/reference/lexical_analysis.html#f-strings)（也简称为f字符串）允许您通过在字符串前加上`f`或者`F`将表达式写为字符串，在字符串中包含Python表达式的值`{expression}`。

可选的格式说明符可以跟在表达式后面。这样可以更好地控制值的格式化方式。以下示例将pi舍入到小数点后的三个位置：

```
>>> import math
>>> print(f'The value of pi is approximately {math.pi:.3f}.')
The value of pi is approximately 3.142.
>>>
```

在该':'字段之后传递一个整数将导致该字段为最小字符数。这对于使列排列很有用。

```
>>> table = {'Sjoerd':4127,'Jack':4098,'Dcab':7678}
>>> for name, phone in table.items():
...     print(f' {name:10} ==> {phone:10d}')
...
 Sjoerd     ==>       4127
 Jack       ==>       4098
 Dcab       ==>       7678
>>>
```



