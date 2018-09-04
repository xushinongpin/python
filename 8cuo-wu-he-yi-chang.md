# 错误和异常

到目前为止，错误消息还没有提到，但是如果你已经尝试过这些例子，你可能已经看过了一些。存在（至少）两种可区分的错误：语法错误和异常。

## 语法错误

语法错误（也称为解析错误）可能是您在学习Python时最常见的抱怨：

```
>>> while True print('Hello world')
  File "<stdin>", line 1
    while True print('Hello world')
                   ^
SyntaxError: invalid syntax
>>>
```

解析器重复出现违规行，并显示一个指向检测到错误的行中最早点的“箭头”。该错误是由箭头前面的标记引起的（或至少在其中检测到的）：在该示例中，在函数处检测到错误print\(\)，因为':'在它之前缺少冒号（）。打印文件名和行号，以便在输入来自脚本时知道查找位置。



## 异常

即使语句或表达式在语法上是正确的，但在尝试执行它时可能会导致错误。在执行期间检测到的错误称为异常，并且不是无条件致命的：您将很快学会如何在Python程序中处理它们。但是，大多数异常都不是由程序处理的，并导致错误消息，如下所示：

```
>>> 10 * (1/0)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
>>> 4 + spam*3
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'spam' is not defined
>>> '2' + 2
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
>>>

```



