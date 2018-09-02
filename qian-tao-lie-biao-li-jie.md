### 嵌套列表理解

列表推导中的初始表达式可以是任意表达式，包括另一个列表推导。

考虑以下3x4矩阵的示例，该矩阵实现为3个长度为4的列表的列表：

```
>>> matrix = [
...      [1,2,3,4],
...      [5,6,7,8],
...      [9,10,11,12],
... ]
>>> [[row[i] for row in matrix] for i in range(4)]
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
>>> # 等效
>>> transposed = []
>>> for i in range(4):
...     transposed.append([row[i] for row in matrix])
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
>>>

反之亦然：
>>> transposed = []
>>> for i in range(4):
...     # the following 3 lines implement the nested listcomp
...     transposed_row = []
...     for row in matrix:
...             transposed_row.append(row[i])
...     transposed.append(transposed_row)
...
>>> transposed
[[1, 5, 9], [2, 6, 10], [3, 7, 11], [4, 8, 12]]
>>>
```



