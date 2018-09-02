## Sets

Python还包括_集合_的数据类型。集合是无序集合，没有重复元素。基本用途包括成员资格测试和消除重复条目。集合对象还支持数学运算，如并集，交集，差异和对称差异。

大括号或[`set()`](https://docs.python.org/3/library/stdtypes.html#set)函数可用于创建集合。注意：要创建一个空集，你必须使用`set()`，而不是`{}`;后者创建一个空字典，一个我们将在下一节讨论的数据结构。

这是一个简短的演示：

```
>>> basket = {'apple','orange','apple','pear','orange','banana'}
>>> print(basket)
{'orange', 'pear', 'apple', 'banana'}
>>> 'orange' in basket
True
>>> 'crabgrass' in basket
False
>>>
>>>
>>> a = set('abracadabra')
>>> b = set('alacazam')
>>> a
{'a', 'd', 'c', 'r', 'b'}
>>> a - b
{'d', 'b', 'r'}
>>> a | b
{'a', 'd', 'z', 'm', 'c', 'r', 'b', 'l'}
>>> a & b
{'a', 'c'}
>>> a ^ b
{'m', 'b', 'r', 'd', 'z', 'l'}
>>>
```

与[列表推导](https://docs.python.org/3/tutorial/datastructures.html#tut-listcomps)类似，也支持集合理解：

```
>>> a = {x for x in 'abracadabra' if x not in 'abc'}
>>> a
{'d', 'r'}
>>>
```



