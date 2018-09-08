## 错误输出重定向和程序终止

该sys模块还具有stdin，stdout和stderr的属性。后者对于发出警告和错误消息非常有用，即使在重定向stdout时也可以看到它们：

```
>>> sys.stderr.write('Warning, log file not found starting a new one\n')
Warning, log file not found starting a new one
47
>>>
```

终止脚本的最直接方法是使用sys.exit\(\)。

