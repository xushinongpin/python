内置列表类型可以满足许多数据结构需求。但是，有时需要具有不同性能权衡的替代实现。

该array模块提供的array\(\)对象类似于仅存储同类数据的列表，并且更紧凑地存储它。以下示例显示了存储为两个字节无符号二进制数（typecode "H"）的数字数组，而不是通常的Python int对象列表的每个条目通常16个字节：

```
>>> from array import array
>>> a = array('H', [4000, 10, 700, 22222])
>>> sum(a)
26932
>>> a[1:3]
array('H', [10, 700])
>>>
```

该collections模块提供的deque\(\)对象类似于列表，具有更快的附加和左侧弹出，但在中间查找较慢。这些对象非常适合实现队列和广度优先树搜索：

```
>>> from collections import deque
>>> d = deque(["task1", "task2", "task3"])
>>> d.append("task4")
>>> print("Handling", d.popleft())
Handling task1
>>> print("Handling", d.popleft())
Handling task2
>>> print("Handling", d.popleft())
Handling task3
>>> print("Handling", d.popleft())
Handling task4
>>> print("Handling", d.popleft())
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: pop from an empty deque
>>>
```

除了替代列表实现之外，该库还提供了其他工具，例如bisect具有用于操作排序列表的函数的模块：

```
>>> import bisect
>>> scores = [(100, 'perl'), (200, 'tcl'), (400, 'lua'), (500, 'python')]
>>> bisect.insort(scores, (300, 'ruby'))
>>> scores
[(100, 'perl'), (200, 'tcl'), (300, 'ruby'), (400, 'lua'), (500, 'python')]
>>>
```



