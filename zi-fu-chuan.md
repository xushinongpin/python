### 字符串

##### 转义符号 \

除了数字之外，Python还可以操作字符串，这可以通过多种方式表达。它们可以用单引号（'...'）或双引号（"..."）括起来，结果相同\[2\]。 \可用于转义引号：

```
>>> 'spam eggs' # single quotes
'spam eggs'
>>> 'doesn\'t' # use \' to escape the single quote...
"doesn't"
>>> "does't" #... or use double quotes instead
"does't"
>>> '"Yes,"they said.'
'"Yes,"they said.'
>>> "\"Yes,\"they said."
'"Yes,"they said.'
>>> '"Isn\'t,"they said.'
'"Isn\'t,"they said.'
>>>
```

##### \r\n

```
>>> '"Isn\'t",they said.'
'"Isn\'t",they said.'
>>> print('"Isn\'t",they said.')
"Isn't",they said.
>>> s='First line. \n Second line.' #\n means newline
>>> s #without print(), \n is included  in the output
'First line. \n Second line.'
>>> print(s) #with print(), \n produces a new line
First line.
 Second line.
>>>
```

##### r

如果您不希望将前面提到的字符\解释为特殊字符，则可以通过在第一个引号之前添加原始字符串来使用原始字符串r：

```
>>> print('C:\some\name') # here \n means newline!
C:\some
ame
>>> print(r'C:\some\name') #note the r before the quote
C:\some\name
>>>
```

##### """

字符串文字可以跨越多行。一种方法是使用三引号： """..."""或'''...'''。行尾自动包含在字符串中，但可以通过\在行尾添加a来防止这种情况

```
>>> print("""\
... Usage: thingy [OPTIONS]
... -h                         Display this usage message
... -H hostname                Hostname to connect to
... """)
Usage: thingy [OPTIONS]
-h                         Display this usage message
-H hostname                Hostname to connect to

>>>
```

##### + 与 \*

字符串可以与+操作符连接（粘合在一起），并重复\*：

```
>>> # 3 times 'un', followed by 'ium'
... 3*'un'+'ium'
'unununium'
>>>

两个或多个彼此相邻的字符串文字（即引号之间的字符串）会自动连接
>>> 'Py' 'thon'
'Python'
>>>
```

##### 断开长字符

```
>>> text = ('Put several strings within parenthese'
...             'to have them joined together.')
>>> text
'Put several strings within parentheseto have them joined together.'
>>>
```

##### 仅适用于两个文字，而不是变量或表达式

```
>>> prefix = 'Py'
>>> prefix 'thon' #can't concatenate variable and a string literal
  File "<stdin>", line 1
    prefix 'thon' #can't concatenate variable and a string literal
                ^
SyntaxError: invalid syntax
>>> ('un'*3) 'ium'
  File "<stdin>", line 1
    ('un'*3) 'ium'
                 ^
SyntaxError: invalid syntax
>>>
```

##### + 【连接变量或变量和文字】

```
>>> prefix = 'Py'
>>> prefix + 'thon'
'Python'
>>>
```

##### 字符串索引【字符串可以被索引（下标），第一个字符具有索引0.没有单独的字符类型; 一个字符只是一个大小为1的字符串】

```
+---+---+---+---+---+---+
 | P | y | t | h | o | n |
 +---+---+---+---+---+---+
 0   1   2   3   4   5   6
-6  -5  -4  -3  -2  -1
例子：
>>> word = 'Python'
>>> word[0] #character in position 0
'P'
>>> word[5] #character in position 5
'n'
>>>
>>> word[-1] #last character
'n'
>>> word[-2] #second-last character
'o'
>>> word[-6]
'P'
>>>

切片

获取单个字符
>>> word[0:2] #characters from position 0 (included) to 2 (excluded)
'Py'
>>> word[2:5] #characters from position 2 (included) to 5 (excluded)
'tho'
>>>

始终包含开始，并始终排除结束
>>> word[:2] + word[2:]
'Python'
>>> word[:4] + word[4:]
'Python'
>>>
>>> word[:2] #character from the beginning to position 2 (excluded)
'Py'
>>> word[4:] #character from position 4 (included) to the end
'on'
>>> word[-2:] #character from the second-last (included) to the end
'on'
>>>

超出索引 - 报错
>>> word[42] # the word only has 6 characters
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: string index out of range
>>>
利用切片防止错误
>>> word[4:42]
'on'
>>> word[42:]
''
>>>

重新分配字符给字符串索引将报错
>>> word[0] = 'J'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
>>> word[2:] = 'py'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'str' object does not support item assignment
>>>

```



