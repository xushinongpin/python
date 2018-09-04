这是一个例子展示了如何引用不同的范围和命名空间，以及如何global和nonlocal影响可变结合：

```
>>> def scope_test():
...     def do_local():
...             spam = "local spam"
...     def do_nonlocal():
...             nonlocal spam
...             spam = "nonlocal spam"
...     def do_global():
...             global spam
...             spam = "global spam"
...     spam = "test spam"
...     do_local()
...     print("After local assignment:", spam)
...     do_nonlocal()
...     print("After nonlocal assignment:", spam)
...     do_global()
...     print("After global assignment:", spam)
...
>>> scope_test()
After local assignment: test spam
After nonlocal assignment: nonlocal spam
After global assignment: nonlocal spam
>>> print("In global scope:", spam)
In global scope: global spam
>>>
```

请注意本地分配（默认）如何不改变scope\_test对垃圾邮件的绑定。该nonlocal分配改变了scope\_test对垃圾邮件的绑定，并且该global分配更改了模块级绑定。

您还可以在分配之前 看到之前没有垃圾邮件绑定global。

