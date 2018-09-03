# 输入输出

## Fancier输出格式

到目前为止，我们遇到了两种写值的方法：_表达式语句_和[`print()`](https://docs.python.org/3/library/functions.html#print)函数。（第三种方法是使用`write()`文件对象的方法;标准输出文件可以作为参考`sys.stdout`。有关详细信息，请参阅库参考。）

通常，您需要更多地控制输出的格式，而不仅仅是打印空格分隔的值。有几种格式化输出的方法。

* 要使用[格式化的字符串文字](https://docs.python.org/3/tutorial/inputoutput.html#tut-f-strings)，请在开始引号或三引号之前`f`或`F`之前开始一个字符串。在这个字符串中，你可以在`{`和`}`字符之间写一个Python表达式，它可以引用变量或文字值。

```
>>> year = 2016; event = 'Referendum'
>>> f'Results of the {year} {event}'
'Results of the 2016 Referendum'
>>>
```

str.format\(\)字符串的方法需要更多的手动操作。您仍将使用{和}标记变量将被替换的位置，并且可以提供详细的格式化指令，但您还需要提供要格式化的信息。

```
>>> yes_votes = 42_572_654 ; no_votes = 43_132_495
>>> percentage = yes_votes/(yes_votes+no_votes)
>>> ' {:-9} YES votes {:2.2%}'.format(yes_votes,percentage)
'  42572654 YES votes 49.67%'
>>>
```

最后，您可以使用字符串切片和连接操作自己完成所有字符串处理，以创建您可以想象的任何布局。字符串类型有一些方法可以执行将字符串填充到给定列宽的有用操作。

当您不需要花哨的输出但只是想快速显示某些变量以进行调试时，您可以将任何值转换为带有repr\(\)或者str\(\)函数的字符串。

该str\(\)函数用于返回值相当于人类可读的值的表示，同时repr\(\)用于生成可由解释器读取的表示（或者SyntaxError如果没有等效语法则强制执行）。对于没有特定人类消费表示的对象，str\(\)将返回相同的值 repr\(\)。许多值，例如数字或结构（如列表和字典），使用任一函数都具有相同的表示。特别是字符串有两个不同的表示。

一些例子：

```
>>> s = 'Hello, world.'
>>> str(s)
'Hello, world.'
>>> repr(s)
"'Hello, world.'"
>>> str(1/7)
'0.14285714285714285'
>>> x = 10 * 3.25
>>> y = 200 * 200
>>> s = 'The value of x is ' + repr(x) + ', and y is ' + repr(y) + '...'
>>> print(s)
The value of x is 32.5, and y is 40000...
>>> # The repr() of a string adds string quotes and backslashes:
... hello = 'hello, world\n'
>>> hellos = repr(hello)
>>> print(hellos)
'hello, world\n'
>>> # The argument to repr() may be any python object:
... repr((x, y, ('spam', 'eggs')))
"(32.5, 40000, ('spam', 'eggs'))"
>>>

```



