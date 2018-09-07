## 操作系统接口

该os模块提供了许多与操作系统交互的功能：

```
>>> import os
>>> os.getcwd()
'/root'
>>> os.chdir('/server/accesslogs')//不存在的路径会报错
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
FileNotFoundError: [Errno 2] No such file or directory: '/server/accesslogs'
>>> os.chdir('/www/wwwroot/python')
>>> os.system('mkdir today')
0
>>>

```



