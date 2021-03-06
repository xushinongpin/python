该[`decimal`](https://docs.python.org/3/library/decimal.html#module-decimal)模块提供[`Decimal`](https://docs.python.org/3/library/decimal.html#decimal.Decimal)十进制浮点运算的数据类型。与[`float`](https://docs.python.org/3/library/functions.html#float)二进制浮点的内置实现相比，该类特别有用

* 财务申请和其他需要精确十进制表示的用途，
* 控制精度，
* 控制四舍五入以满足法律或监管要求，
* 跟踪有效小数位，或
* 用户希望结果与手工完成的计算相匹配的应用程序。

例如，计算70美分手机费用的5％税，会产生十进制浮点和二进制浮点数的不同结果。如果结果四舍五入到最接近的分数，则差异变得很大：

```
>>> from decimal import *
>>> round(Decimal('0.70') * Decimal('1.05'), 2)
Decimal('0.74')
>>> round(.70 * 1.05, 2)
0.73
>>>
```

该Decimal结果保留尾随零，自动推断来自两个地方的意义被乘数4点地方的意义。Decimal可以手动复制数学，避免了二进制浮点不能精确表示十进制数时可能出现的问题。

精确表示使Decimal类能够执行不适合二进制浮点的模数计算和相等性测试：

```
>>> Decimal('1.00') % Decimal('.10')
Decimal('0.00')
>>> 1.00 % 0.10
0.09999999999999995
>>> sum([Decimal('0.1')]*10) == Decimal('1.0')
True
>>> sum([0.1]*10) == 1.0
False
>>>
```

该decimal模块提供了所需的精度算术：

```
>>> getcontext().prec = 36
>>> Decimal(1) / Decimal(7)
Decimal('0.142857142857142857142857142857142857')
>>>
```



