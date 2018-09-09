Python执行自动内存管理（大多数对象的引用计数和 垃圾收集以消除循环）。在消除了对最后一次引用后不久释放的内存。

这种方法适用于大多数应用程序，但偶尔需要跟踪对象，只要它们被其他东西使用。不幸的是，只是跟踪它们会创建一个使它们永久化的引用。该weakref模块提供了跟踪对象的工具，而无需创建引用。当不再需要该对象时，它将自动从weakref表中删除，并为weakref对象触发回调。典型应用程序包括缓存创建成本高昂的对象：

```
>>> import weakref, gc
>>> class A:
...     def __init__(self, value):
...             self.value = value
...     def __repr__(self):
...             return str(self.value)
...
>>> a = A(10)                   # create a reference
>>> d = weakref.WeakValueDictionary()
>>> d['primary'] = a            # does not create a reference
>>> d['primary']                # fetch the object if it is still alive
10
>>> del a
>>> gc.collect()                # run garbage collection right away
28
>>> d['primary']                # entry was automatically removed
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/usr/local/bin/python3/lib/python3.7/weakref.py", line 137, in __getitem__
    o = self.data[key]()
KeyError: 'primary'
>>>

```



