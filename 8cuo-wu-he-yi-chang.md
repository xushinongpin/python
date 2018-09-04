# 错误和异常

到目前为止，错误消息还没有提到，但是如果你已经尝试过这些例子，你可能已经看过了一些。存在（至少）两种可区分的错误：语法错误和异常。

## 语法错误

语法错误（也称为解析错误）可能是您在学习Python时最常见的抱怨：

```
>>> while True print('Hello world')
  File "<stdin>", line 1
    while True print('Hello world')
                   ^
SyntaxError: invalid syntax
>>>

```



