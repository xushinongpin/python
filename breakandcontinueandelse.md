在break声明中，类似于C，爆发最内层的 for或while循环。

循环语句可能有一个else子句; 当循环通过列表耗尽（with for）或条件变为false（with while）时终止，但是当循环被break语句终止时不执行它。这通过以下循环来举例说明，该循环搜索素数：

```
>>> for n in range(2,10):
...     for x in range(2,n):
...             if n % x == 0:
...                     print(n,'equals',x,'*',n//x)
...                     break
...     else:
...             # loop fell through without finding a factor
...             print(n,'is a prime number')
...
2 is a prime number
3 is a prime number
4 equals 2 * 2
5 is a prime number
6 equals 2 * 3
7 is a prime number
8 equals 2 * 4
9 equals 3 * 3
>>>

```



