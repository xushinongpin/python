### 使用列表作为堆栈

list方法可以很容易地将列表用作堆栈，其中添加的最后一个元素是检索到的第一个元素（“last-in，first-out”）。要将项添加到堆栈顶部，请使用append\(\)。要从堆栈顶部检索项目，请在pop\(\)没有显式索引的情况下使用。例如：

```
>>> stack = [3,4,5]
>>> stack.append(6)
>>> stack.append(7)
>>> stack
[3, 4, 5, 6, 7]
>>> stack.pop()
7
>>> stack
[3, 4, 5, 6]
>>> stack.pop()
6
>>> stack.pop()
5
>>> stack
[3, 4]
>>>
```



