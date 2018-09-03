### 格式化字符串文字

[格式化的字符串文字](https://docs.python.org/3/reference/lexical_analysis.html#f-strings)（也简称为f字符串）允许您通过在字符串前加上`f`或者`F`将表达式写为字符串，在字符串中包含Python表达式的值`{expression}`。

可选的格式说明符可以跟在表达式后面。这样可以更好地控制值的格式化方式。以下示例将pi舍入到小数点后的三个位置：

```
>>> import math
>>> print(f'The value of pi is approximately {math.pi:.3f}.')
The value of pi is approximately 3.142.
>>>
```



