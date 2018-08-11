我们可以创建一个将Fibonacci系列写入任意边界的函数：

```
>>> def fib(n): #write Fibonacci series up to n
...     """Print a Fibonacci series up to n."""
...     a,b = 0,1
...     while a < n:
...             print(a,end=" ")
...             a,b = b,a+b
...     print()
...
>>> #Nuw call the function we just defined:
... fib(2000)
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
>>>
```

该关键字def引入了一个函数定义。它必须后跟函数名称和带括号的形式参数列表。构成函数体的语句从下一行开始，并且必须缩进。

函数体的第一个语句可以选择是字符串文字; 此字符串文字是函数的文档字符串或docstring。（有关文档字符串的更多信息，请参阅文档字符串部分。）有些工具使用文档字符串自动生成在线或印刷文档，或者让用户以交互方式浏览代码; 在您编写的代码中包含docstrings是一种很好的做法，所以要养成习惯。

函数的执行引入了用于函数局部变量的新符号表。更准确地说，函数中的所有变量赋值都将值存储在本地符号表中; 而变量引用首先在本地符号表中查找，然后在封闭函数的本地符号表中查找，然后在全局符号表中查找，最后在内置名称表中查找。因此，全局变量不能直接在函数内赋值（除非在global语句中命名），尽管可以引用它们。

调用函数调用的实际参数（参数）在被调用函数的本地符号表中引入; 因此，使用call by value传递参数（其中值始终是对象引用，而不是对象的值）。\[1\]当函数调用另一个函数时，将为该调用创建一个新的本地符号表。

函数定义在当前符号表中引入函数名称。函数名称的值具有解释器将其识别为用户定义函数的类型。此值可以分配给另一个名称，该名称也可以用作函数。这是一般的重命名机制：

```
>>> fib
<function fib at 0x7f42738ee8c8>
>>> f = fib
>>> f(100)
0 1 1 2 3 5 8 13 21 34 55 89
>>>
```

来自其他语言，您可能会反对这fib不是一个函数而是一个过程，因为它不返回值。实际上，即使是没有return语句的函数也会 返回一个值，尽管它是一个相当无聊的值。调用此值None（它是内置名称）。None如果它是唯一写入的值，则解释器通常会禁止写入值。如果你真的想使用它，你可以看到它print\(\)：

```
>>> fib(0)

>>> print(fib(0))

None
>>>
```

编写一个函数可以很简单地返回Fibonacci系列的数字列表，而不是打印它：

```
>>> def fib2(n): # return Fibonacci series up to n
...     """Return a list containing the fibonacci series up to n"""
...     result = []
...     a,b = 0,1
...     while a < n:
...             result.append(a) #see below
...             a,b = b,a+b
...     return result
...
>>> f100 = fib2(100) #call it
>>> f100  #write the result
[0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89]
>>>
```

像往常一样，此示例演示了一些新的Python功能：

该return语句返回一个函数的值。 return没有表达式参数返回None。从函数的末尾掉落也会返回None。

该语句result.append\(a\)调用list对象 的方法result。方法是“属于”对象并被命名的函数 obj.methodname，其中obj是某个对象（这可能是表达式），并且methodname是由对象的类型定义的方法的名称。不同类型定义不同的方法。不同类型的方法可以具有相同的名称而不会引起歧义。（可以使用类定义自己的对象类型和方法，请参阅类）append\(\)示例中显示的方法是为列表对象定义的; 它在列表的末尾添加了一个新元素。在这个例子中它相当于 ，但效率更高。result = result + \[a\]

### 默认参数值

```
>>> def ask_ok(prompt,retries=4,reminder='Please try again!'):
...     while True:
...             ok = input(prompt)
...             if ok in ('y','ye','yes'):
...                     return True
...             if ok in ('n','no','nop','nope'):
...                     return false
...             retries = retries - 1
...             if retries < 0:
...                     raise ValueError('invalid user response')
...             print(reminder)
...
>>> ask_ok('Do you really want to quit?')
Do you really want to quit?yy
Please try again!
Do you really want to quit?y
True
>>> ask_ok('OK to overwrite the file?',2)
OK to overwrite the file?yy
Please try again!
OK to overwrite the file?y
True
>>> ask_ok('OK to overwrite the file?',2,'Come on,only yes or no!')
OK to overwrite the file?y
True
>>>
```

默认值在定义范围内的函数定义点进行计算 ，以便进行

```
>>> i = 5
>>> def f(arg=i):
...     print(arg)
...
>>> i = 6
>>> f()
5
>>> f(8)
8
>>>
```

默认值变量累加【重要警告： 默认值仅评估一次。当默认值是可变对象（例如列表，字典或大多数类的实例）时，这会产生差异。例如，以下函数会累积在后续调用中传递给它的参数：】

```
>>> def f(a,L=[]):
...     L.append(a)
...     return L
...
>>> print(f(1))
[1]
>>> print(f(1))
[1, 1]
>>> print(f(2))
[1, 1, 2]
>>> print(f(3))
[1, 1, 2, 3]
>>>

不要调用共享默认值
>>> def f(a,L=None):
...     if L is None:
...             L = []
...     L.append(a)
...     return L
...
>>> print(f(1))
[1]
>>> print(f(2))
[2]
>>> print(f(3))
[3]
>>>
```

关键字参数

```
>>> def parrot(voltage,state='a stiff',action='voom',type='Norwegian Blue'):
...     print("-- This parrot would't",action,end=' ')
...     print("if you put",voltage,'volts through it.')
...     print("-- Lovely plumage, the",type)
...     print("-- It's",state,"!")
...
>>> parrot(1)
-- This parrot would't voom if you put 1 volts through it.
-- Lovely plumage, the Norwegian Blue
-- It's a stiff !
>>>
```

更多例子详见 [此处](https://docs.python.org/3/tutorial/controlflow.html)

### 任意参数列表

```
>>> def write_multiple_items(file,separator,*args):
...     file.write(scparator.json(args))
...
>>>
```

### 解压缩参数列表

```
>>> list(range(3,6))
[3, 4, 5]
>>> args = [3,6]
>>> list(range(*args))
[3, 4, 5]
>>>

>>> list(range(3,6))
[3, 4, 5]
>>> list(range(*args))
[3, 4, 5]
>>> args = [3,6]
>>>
```

### Lambda表达式

可以使用lambda关键字创建小的匿名函数。此函数返回其两个参数的总和：。Lambda函数可以在需要函数对象的任何地方使用。它们在语法上限于单个表达式。从语义上讲，它们只是正常函数定义的语法糖。与嵌套函数定义一样，lambda函数可以引用包含范围的变量：lambda a, b: a+b

```
>>> def make_incrementor(n):
...     return lambda x: x+n
...
>>> f = make_incrementor(42)
>>> f(0)
42
>>> f(1)
43
>>>
```

传递一个小函数作为参数

```
>>> pairs = [(1,'one'),(2,'two'),(3,'three'),(4,'fout')]
>>> pairs.sort(key=lambda pair: pair[1])
>>> pairs
[(4, 'fout'), (1, 'one'), (3, 'three'), (2, 'two')]
>>>
```

### 文档字符串

以下是有关文档字符串的内容和格式的一些约定。

第一行应始终是对象目的的简短概述。为简洁起见，它不应显式声明对象的名称或类型，因为这些可通过其他方式获得（除非名称恰好是描述函数操作的动词）。该行应以大写字母开头，以句点结尾。

如果文档字符串中有更多行，则第二行应为空白，从而在视觉上将摘要与其余描述分开。以下行应该是一个或多个段落，描述对象的调用约定，其副作用等。

Python解析器不会从Python中删除多行字符串文字的缩进，因此处理文档的工具必须在需要时删除缩进。这是使用以下约定完成的。字符串第一行之后的第一个非空行 确定整个文档字符串的缩进量。（我们不能使用第一行，因为它通常与字符串的开头引号相邻，因此它的缩进在字符串文字中不明显。）然后从字符串的所有行的开头剥离与该缩进“等效”的空格。 。缩进的行不应该出现，但是如果它们出现，则应该剥离它们的所有前导空格。应在扩展标签后测试空白的等效性（通常为8个空格）。

以下是多行文档字符串的示例：

```
>>> def my_function():
...     """Do nothing, but document it.
...
...     No, really, it doesn't do anything.
...     """
...     pass
...
>>> print(my_function.__doc__)
Do nothing, but document it.

        No, really, it doesn't do anything.

>>>

```



