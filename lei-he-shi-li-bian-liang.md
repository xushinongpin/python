一般来说，实例变量是针对每个实例唯一的数据，而类变量是针对类的所有实例共享的属性和方法：

```
>>> class Dog:
...     def __init__(self, name):
...             self.name = name
...             self.tricks = []    # creates a new empty list for each dog
...     def add_trick(self, trick):
...             self.tricks.append(trick)
...
>>> d = Dog('Fido')
>>> e = Dog('Buddy')
>>> d.add_trick('roll over')
>>> e.add_trick('play dead')
>>> d.tricks
['roll over']
>>> e.tricks
['play dead']
>>>
```



