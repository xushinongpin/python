## 文件通配符

该glob模块提供了从目录通配符搜索中创建文件列表的功能：

```
>>> import os
>>> os.chdir('/www/wwwroot/python')
>>> import glob
>>> glob.glob('*.py')
['workfile.py', 'fibo.py']
>>>
```



