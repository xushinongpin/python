## 模板

该string模块包括一个通用Template类，其语法简化，适合最终用户编辑。这允许用户自定义他们的应用程序而无需更改应用程序。

该格式使用由$有效的Python标识符（字母数字字符和下划线）组成的占位符名称。使用大括号围绕占位符允许其后跟更多的字母数字字母，没有中间空格。写作$$会创建一个转义$：

```
>>> from string import Template
>>> t = Template('${village}folk send $$10 to $cause.')
>>> t.substitute(village='Nottingham', cause='the ditch fund')
'Nottinghamfolk send $10 to the ditch fund.'
>>>

```



