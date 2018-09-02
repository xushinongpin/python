## 循环技术

循环遍历字典时，可以使用该items\(\)方法同时检索密钥和相应的值。

```
>>> knights = {'gallahad':'the pure','robin':'the brave'}
>>> for k,v in knights.items():
...     print(k,v)
...
gallahad the pure
robin the brave
>>>
```

循环遍历序列时，可以使用该enumerate\(\)函数同时检索位置索引和相应的值。

```
>>> for i, v in enumerate(['tic','tac','toe']):
...     print(i, v)
...
0 tic
1 tac
2 toe
>>>
```

要同时循环两个或更多个序列，条目可以与该zip\(\)功能配对。

```
>>> questions = [' name','quest','favorite color']
>>> answers = ['lancelot','the holy grail','blue']
>>> for q, a in zip(questions, answers):
...     print('What is your {0}? It is {1}.'.format(q, a))
...
What is your  name? It is lancelot.
What is your quest? It is the holy grail.
What is your favorite color? It is blue.
```

要反向循环序列，首先在正向指定序列，然后调用该[`reversed()`](https://docs.python.org/3/library/functions.html#reversed)函数。

```
>>> for i in reversed(range(1,10,2)):
...     print(i)
...
9
7
5
3
1
>>> for i in reversed(range(1,10,3)):
...     print(i)
...
7
4
1
>>>
```

要按排序顺序循环序列，请使用sorted\(\)返回新排序列表的函数，同时保持源不变。

```
>>> basket = ['apple','orange','apple','pear','orange','banana']
>>> for f in sorted(set(basket)):
...     print(f)
...
apple
banana
orange
pear
>>>
```

当你循环它时，有时很有可能改变一个列表; 但是，创建新列表通常更简单，更安全。

```
>>> import math
>>> raw_data = [56.2,float('NaN'),51.7,55.3,52.5,float('NaN'),47.8]
>>> filtered_data = []
>>> for value in raw_data:
...     if not math.isnan(value):
...             filtered_data.append(value)
...
>>> filtered_data
[56.2, 51.7, 55.3, 52.5, 47.8]
>>>

```



