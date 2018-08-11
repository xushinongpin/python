注意 换行空格 问题

错

```
>>> # fibonacci series
... #the sum of two elements defines the next
... a,b = 0,1
>>> while a < 10:
... print(a)
  File "<stdin>", line 2
    print(a)
        ^
IndentationError: expected an indented block
>>>
```

对

```
>>> # fibonacci series
... #the sum of two elements defines the next
... a,b = 0,1
>>> while a < 10:
...      print(a)
...      a,b =b,a+b
...
0
1
1
2
3
5
8
>>>

```



