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

（是的，这是正确的代码，仔细一看：该else条款属于for循环，不是的if。陈述）

当循环使用，该else条款有更多的共同点与 else一个条款try声明比它认为的 if语句：一个try语句的else时候也不例外条款发生运行和循环的else条款时没有运行break 发生。有关try语句和异常的更多信息，请参阅 [处理异常](https://docs.python.org/3/tutorial/errors.html#tut-handling)。

该continue声明也是从C借用的，继续循环的下一次迭代：

```
>>> for num in range(2,10):
...     if num % 2 == 0:
...             print("Found an even number",num)
...             continue
...     print("Found a number",num)
...
Found an even number 2
Found a number 3
Found an even number 4
Found a number 5
Found an even number 6
Found a number 7
Found an even number 8
Found a number 9
>>>

```



