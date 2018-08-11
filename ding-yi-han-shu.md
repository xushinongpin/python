我们可以创建一个将Fibonacci系列写入任意边界的函数：

```
>>> def fib(n): #write Fibonacci series up to n
...     """Print a Fibonacci series up to n."""
...     a,b = 0,1
...     while a < n:
...             print(a,end=" ")
...             a,b = b,a+b
...     print()
...
>>> #Nuw call the function we just defined:
... fib(2000)
0 1 1 2 3 5 8 13 21 34 55 89 144 233 377 610 987 1597
>>>

```



