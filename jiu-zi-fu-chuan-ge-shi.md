### 旧字符串格式

该%运营商还可以用于字符串格式化。它将左参数解释为非常类似于sprintf\(\)要应用于右参数的格式字符串，并返回由此格式化操作产生的字符串。例如：

```
>>> import math
>>> print('The value of pi is approximately %5.3f.' % math.pi)
The value of pi is approximately 3.142.
>>>
```



