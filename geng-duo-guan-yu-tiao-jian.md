## 更多关于条件

while和if语句中使用的条件可以包含任何运算符，而不仅仅是比较。

比较运算符in并检查序列中是否出现（不发生）值。运算符并比较两个对象是否真的是同一个对象; 这只对像列表这样的可变对象很重要。所有比较运算符具有相同的优先级，低于所有数值运算符的优先级。not inisis not

比较可以链接。例如，测试是否小于，而且等于。a &lt; b == cabbc

比较可以使用布尔运算符进行组合and和or，和一个比较的结果（或任何其它的布尔表达式的）可以与否定not。这些优先级低于比较运算符; 它们之间，not具有最高优先级和or最低优先级，因此相当于。与往常一样，括号可用于表达所需的组成。A and not B or C\(A and \(not B\)\) or C

布尔运算符and和or所谓的短路 运算符：它们的参数从左到右进行计算，一旦确定结果，评估就会停止。例如，如果A且C为true但B为false，则不评估表达式 。当用作一般值而不是布尔值时，短路运算符的返回值是最后一个求值的参数。A and B and CC

可以将比较结果或其他布尔表达式分配给变量。例如，

```
>>> string1,string2,string3 = '','trondheim','Hammer Dance'
>>> non_null = string1 or string2 or string3
>>> non_null
'trondheim'
>>>
```

请注意，在Python中，与C不同，赋值不能出现在表达式中。C程序员可能会抱怨这一点，但它避免了C程序中遇到的常见问题：=在==预期时输入表达式。

