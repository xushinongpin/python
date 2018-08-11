加减乘除

```
>>> 2+2
4
>>> 50-5*6
20
>>> (50-5*6)/4
5.0
>>> 8/5 #division alway returns a floating point number
1.6
>>>
```

浮点数

```
>>> 17/3 #classic division returns a float
5.666666666666667
>>> 17 // 3 # floor division discards the fractional part
5
>>> 17 % 3 #the % operator returns the remainder of the division
2
>>> 5*3+2 #result * divisor remainder
17
>>>
```

幂运算

```
>>> 5**2 # 5 square
25
>>> 2**7 # 2 to the power of 7
128
>>>
```

= 赋值

```
>>> width = 20
>>> height = 5* 9
>>> width * height
900
>>>
```

未定义变量赋值将会报错

```
>>> n #try to access an undefined variable
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'n' is not defined
```

浮点数完全支持;具有混合类型操作数的运算符将整数操作数转换为浮点数：

```
>>> 4*3.75
15.0
>>> 4*3.75  -1
14.0
>>>
```

```
在交互模式下，最后打印的表达式将分配给变量 _。这意味着当您使用Python作为桌面计算器时，继续计算会更容易一些>>> tax = 12.5/100
>>> price = 100.50
>>> price * tax
12.5625
>>> price +_
113.0625
>>> round(_,2)
113.06
>>>
```

由于\*\*具有更高的优先级-，-3\*\*2将被解释为-\(3\*\*2\)从而导致-9。要避免这种情况并获得9，您可以使用\(-3\)\*\*2。

