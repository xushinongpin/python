### 手动字符串格式

这是同一个正方形和立方体表，手动格式化：

```
>>> for x in range(1, 11):
...     print(repr(x).rjust(2),repr(x*x).rjust(3),end=' ')
...     # Note use of 'end' on previous line
...     print(repr(x*x*x).rjust(4))
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
>>>

```



