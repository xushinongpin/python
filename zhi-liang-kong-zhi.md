## 质量控制

开发高质量软件的一种方法是在开发过程中为每个函数编写测试，并在开发过程中经常运行这些测试。

该doctest模块提供了一个工具，用于扫描模块并验证程序文档字符串中嵌入的测试。测试构造就像将典型调用及其结果剪切并粘贴到文档字符串一样简单。这通过向用户提供示例来改进文档，并且它允许doctest模块确保代码保持对文档的真实性：

```
>>> def average(values):
...     """Computes the arithmetic mean of a list of numbers.
...     print(average([20, 30, 70]))
...     40.0
...     """
...     return sum(values) / len(values)
...
>>> import doctest
>>> doctest.testmod()   # automatically validate the embedded tests
TestResults(failed=0, attempted=0)
>>>

```

该unittest模块不像模块那样轻松doctest，但它允许在单独的文件中维护更全面的测试集：

```
>>> import unittest
>>> class TestStatisticalFunctions(unittest.TestCase):
...     def test_average(self):
...             self.assertEqual(average([20, 30, 70]), 40.0)
...             self.assertEqual(round(average([1, 5, 7]), 1), 4.3)
...             with self.assertRaises(ZeroDivisionError):
...                     average([])
...             with self.assertRaises(TypeError):
...                     average(20, 30, 70)
...
>>> unittest.main()  # Calling from the command line invokes all tests
.
----------------------------------------------------------------------
Ran 1 test in 0.000s

OK
[root@localhost ~]#

```



