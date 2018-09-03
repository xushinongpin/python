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



