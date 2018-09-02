### 使用列表作为队列

也可以使用列表作为队列，其中添加的第一个元素是检索的第一个元素（“先进先出”）; 但是，列表不能用于此目的。虽然列表末尾的追加和弹出很快，但是从列表的开头进行插入或弹出是很慢的（因为所有其他元素都必须移动一个）。

要实现队列，请使用[collections.deque](https://docs.python.org/3/library/collections.html#collections.deque)设计为具有快速追加和从两端弹出的队列。例如：

```
>>> from collections import deque
>>> queue = deque(["Eric","John","Michael"])
>>> queue.append("Terry")
>>> queue.append("Graham")
>>> queue.popleft()
'Eric'
>>> queue.popleft()
'John'
>>> queue
deque(['Michael', 'Terry', 'Graham'])
>>>
```



