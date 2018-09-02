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



