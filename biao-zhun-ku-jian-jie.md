# 标准库简介

第二次巡演涵盖了支持专业编程需求的更高级模块。这些模块很少出现在小脚本中。



## 输出格式

该reprlib模块提供了一个repr\(\)定制版本，用于缩放大型或深层嵌套容器的显示：

```
>>> import reprlib
>>> reprlib.repr(set('supercalifragilisticexpialidocious'))
"{'a', 'c', 'd', 'e', 'f', 'g', ...}"
>>>
```



