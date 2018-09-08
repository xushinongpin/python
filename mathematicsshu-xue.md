该math模块提供对浮点数学的底层C库函数的访问：

```
>>> import math
>>> math.cos(math.pi / 4)
0.7071067811865476
>>> math.log(1024, 2)
10.0
>>>
```

该random模块提供了进行随机选择的工具：

```
>>> import random
>>> random.choice(['apple', 'pear', 'banana'])
'pear'
>>> random.choice(['apple', 'pear', 'banana'])
'banana'
>>> random.sample(range(100), 10)   # sampling without replacement
[56, 25, 22, 21, 33, 0, 51, 42, 99, 89]
>>> random.random()    # random float
0.06851663782525674
>>> random.random()    # random float
0.19055429367068755
>>> random.randrange(6)    # random integer chosen from range(6)
4

```



