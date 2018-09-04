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

错误消息的最后一行表明发生了什么。异常有不同的类型，类型作为消息的一部分打印出来：示例中的类型是ZeroDivisionError，NameError和TypeError。作为异常类型打印的字符串是发生的内置异常的名称。对于所有内置异常都是如此，但对于用户定义的异常不一定是这样（尽管它是一个有用的约定）。标准异常名称是内置标识符（不是保留关键字）。

该行的其余部分根据异常类型及其原因提供详细信息。

错误消息的前一部分以堆栈回溯的形式显示发生异常的上下文。通常它包含列出源代码行的堆栈回溯; 但是，它不会显示从标准输入读取的行。

内置异常列出了内置异常及其含义。

## 处理异常

可以编写处理所选异常的程序。请查看以下示例，该示例要求用户输入，直到输入有效整数，但允许用户中断程序（使用Control-C或操作系统支持的任何内容）; 请注意，通过引发KeyboardInterrupt异常来发出用户生成的中断信号。

```
>>> while True:
...     try:
...             x = int(input("Please enter a number: "))
...             break
...     except ValueError:
...             print("Oops! That was no valid number. Try again...")
...
Please enter a number: qwe
Oops! That was no valid number. Try again...
Please enter a number: 1
>>>
```

该try声明的工作原理如下。

首先，执行try子句（try和 except关键字之间的语句）。

如果没有发生异常，则跳过except子句并try完成语句的执行 。

如果在执行try子句期间发生异常，则跳过该子句的其余部分。然后，如果其类型匹配在except关键字后面命名的异常 ，则执行except子句，然后在try语句之后继续执行。

如果发生的异常与except子句中指定的异常不匹配，则将其传递给外部try语句; 如果没有找到处理程序，则它是一个未处理的异常，执行将停止并显示如上所示的消息。

## 提高异常

该raise语句允许程序员强制发生指定的异常。例如：

```
>>> raise NameError('HiThere')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: HiThere
>>>
```

唯一的参数raise表示要引发的异常。这必须是异常实例或异常类（派生自的类Exception）。如果传递了一个异常类，它将通过调用没有参数的构造函数来隐式实例化：

```
>>> raise ValueError # shorthand for 'raise ValueError()'
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ValueError
>>>
```

如果您需要确定是否引发了异常但不打算处理它，则更简单的raise语句形式允许您重新引发异常：

```
>>> try:
...     raise NameError('HiThere')
... except NameError:
...     print('An exception flew by!')
...     raise
...
An exception flew by!
Traceback (most recent call last):
  File "<stdin>", line 2, in <module>
NameError: HiThere
>>>

```



