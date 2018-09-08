## 字符串模式匹配

该re模块为高级字符串处理提供正则表达式工具。对于复杂的匹配和操作，正则表达式提供了简洁，优化的解决方案：

```
>>> import re
>>> re.findall(r'\bf[a-z]*', 'which foot or hand fell fastest')
['foot', 'fell', 'fastest']
>>> re.sub(r'(\b[a-z]+) \1', r'\1', 'cat in the the hat')
'cat in the hat'
>>> 'tea for too'.replace('too', 'two')
'tea for two'
>>>
```



