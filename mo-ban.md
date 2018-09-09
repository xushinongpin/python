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

该substitute\(\)方法KeyError在字典或关键字参数中未提供占位符时引发。对于邮件合并样式应用程序，用户提供的数据可能不完整， safe\_substitute\(\)方法可能更合适 - 如果数据丢失，它将保持占位符不变：

```
>>> t = Template('Return the $item to $owner.')
>>> d = dict(item='unladen swallow')
>>> t.substitute(d)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "/usr/local/bin/python3/lib/python3.7/string.py", line 128, in substitute
    return self.pattern.sub(convert, self.template)
  File "/usr/local/bin/python3/lib/python3.7/string.py", line 121, in convert
    return str(mapping[named])
KeyError: 'owner'
>>> t.safe_substitute(d)
'Return the unladen swallow to $owner.'
>>>

```

模板子类可以指定自定义分隔符。例如，照片浏览器的批量重命名实用程序可以选择对占位符使用百分号，例如当前日期，图像序列号或文件格式：

```
>>> import time, os.path
>>> photofiles = ['img_1074.jpg', 'img_1076.jpg', 'img_1077.jpg']
>>> class BatchRename(Template):
...     delimiter = '%'
...
>>> fmt = input('Enter rename style (%d-date %n-seqnum %f-format):  ')
Enter rename style (%d-date %n-seqnum %f-format):  Ashley_%n%f
>>> t = BatchRename(fmt)
>>> date = time.strftime('%d%b%y')
>>> for i, filename in enumerate(photofiles):
...     base, ext = os.path.splitext(filename)
...     newname = t.substitute(d=date, n=i, f=ext)
...     print('{0} --> {1}'.format(filename, newname))
...
img_1074.jpg --> Ashley_0.jpg
img_1076.jpg --> Ashley_1.jpg
img_1077.jpg --> Ashley_2.jpg
>>>

```

模板的另一个应用是将程序逻辑与多种输出格式的细节分开。这样就可以替换XML文件，纯文本报告和HTML Web报告的自定义模板。

