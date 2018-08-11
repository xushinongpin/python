for

forPython中的语句与您在C或Pascal中使用的语句略有不同。而不是总是迭代数字的算术级数（如在Pascal中），或者让用户能够定义迭代步骤和暂停条件（如C），Python的for语句迭代任何序列的项目（列表或string），按照它们出现在序列中的顺序。例如（没有双关语）：

```
>>> # Measure some strings:
... words = ['cat','window','defenestrate']
>>> for w in words:
...     print(w,len(w))
...
cat 3
window 6
defenestrate 12
>>>

```

如果您需要修改在循环内迭代的序列（例如复制所选项目），建议您先复制一份。迭代序列不会隐式地复制。切片表示法使这特别方便：

```
>>> for w in words[:]:
...     if len(w) > 6:
...             words.insert(0,w)
...
>>> words
['defenestrate', 'cat', 'window', 'defenestrate']
>>>

```



