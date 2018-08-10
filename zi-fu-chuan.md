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



