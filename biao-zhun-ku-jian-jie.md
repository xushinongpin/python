# 标准库简介

第二次巡演涵盖了支持专业编程需求的更高级模块。这些模块很少出现在小脚本中。

## 输出格式

该reprlib模块提供了一个repr\(\)定制版本，用于缩放大型或深层嵌套容器的显示：

```
>>> import reprlib
>>> reprlib.repr(set('supercalifragilisticexpialidocious'))
"{'a', 'c', 'd', 'e', 'f', 'g', ...}"
>>>
```

该pprint模块提供了更加复杂的控制，可以以解释器可读的方式打印内置和用户定义的对象。当结果长于一行时，“漂亮的打印机”会添加换行符和缩进以更清楚地显示数据结构：

```
>>> import pprint
>>> t = [[[['black', 'cyan'], 'white', ['green', 'red']], [['magenta',
...     'yellow'], 'blue']]]
>>> pprint.pprint(t, width=30)
[[[['black', 'cyan'],
   'white',
   ['green', 'red']],
  [['magenta', 'yellow'],
   'blue']]]
>>>
```

该textwrap模块格式化文本段落以适合给定的屏幕宽度：

```
>>> import textwrap
>>> doc = """The wrap() method is just like fill() except that it returns
... a list of strings instead of one big string with newlines to separate
... the wrapped lines."""
>>> print(textwrap.fill(doc, width=40))
The wrap() method is just like fill()
except that it returns a list of strings
instead of one big string with newlines
to separate the wrapped lines.
>>>
```

该locale模块访问文化特定数据格式的数据库。locale格式函数的分组属性提供了使用组分隔符格式化数字的直接方法：

```
>>> import locale
>>> locale.setlocale(locale.LC_ALL, 'English_United States.1252')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/usr/local/bin/python3/lib/python3.7/locale.py", line 604, in setlocale
    return _setlocale(category, locale)
locale.Error: unsupported locale setting
>>> conv = locale.localeconv()          # get a mapping of conventions
>>> x = 1234567.8
>>> locale.format("%d", x, grouping=True)
'1234567'
>>> locale.format_string("%s%.*f", (conv['currency_symbol'],
...     conv['frac_digits'], x), grouping=True)
'1234567.8000000000465661287307739257812500000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000'
>>>

```



