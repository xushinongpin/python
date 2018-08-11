if

可以有零个或多个elif零件，else零件是可选的。关键字' elif'是'else if'的缩写，有助于避免过度缩进。一 if... ... elif... ... elif... ...序列的替代switch或 case其它语言中的语句。

```
>>> x = int(input("Please enter an integer: "))
Please enter an integer: 42
>>> if x < 0:
...     x = 0
...     print('Negative changed to zero')
... elif x == 0:
...     print('Zero')
... elif x == 1:
...     print('Single')
... else:
...     print('More')
...
More
>>>

```



