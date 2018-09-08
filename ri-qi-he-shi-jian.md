## 日期和时间

该datetime模块提供了以简单和复杂的方式操作日期和时间的类。虽然支持日期和时间算法，但实现的重点是有效的成员提取以进行输出格式化和操作。该模块还支持时区感知的对象。

```
>>> # dates are easily constructed and formatted
... from datetime import date
>>> now = date.today()
>>> now
datetime.date(2018, 9, 9)
>>> now.strftime("%m-%d-%y. %d %b %Y is a %A on the %d day of %B.")
'09-09-18. 09 Sep 2018 is a Sunday on the 09 day of September.'
>>> # dates support calendar arithmetic
... birthday = date(1964, 7, 31)
>>> age = now - birthday
>>> age.days
19763
>>>

```



