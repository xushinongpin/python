# 14.交互式输入编辑和历史替换

某些版本的Python解释器支持编辑当前输入行和历史记录替换，类似于Korn shell和GNU Bash shell中的设施。这是使用[GNU Readline](https://tiswww.case.edu/php/chet/readline/rltop.html)库实现的，它支持各种编辑样式。这个库有自己的文档，我们不会在这里复制。

## 14.1。标签完成和历史编辑

在解释器启动时[自动启用](https://docs.python.org/3/library/site.html#rlcompleter-config)变量和模块名称的完成，以便Tab密钥调用完成功能;它查看Python语句名称，当前局部变量和可用模块名称。对于诸如的虚线表达式`string.a`，它将评估表达式直到最终`'.'`，然后根据结果对象的属性建议完成。请注意，如果带有[`__getattr__()`](https://docs.python.org/3/reference/datamodel.html#object.__getattr__)方法的对象是表达式的一部分，则可以执行应用程序定义的代码。默认配置还会将历史记录保存到`.python_history`用户目录中指定的文件中。在下一次互动口译会议期间，历史记录将再次出现。

## 14.2。交互式解释器的替代方案

与早期版本的翻译相比，这个设施向前迈出了一大步;但是，还有一些愿望：如果在连续行上建议了适当的缩进（解析器知道下一个是否需要缩进标记），那将会很好。完成机制可能使用解释器的符号表。检查（或甚至建议）匹配括号，引号等的命令也是有用的。

[IPython](https://ipython.org/)是一种替代的增强型交互式解释器，它具有很长一段时间，它具有标签完成，对象探索和高级历史管理功能。它还可以彻底定制并嵌入到其他应用程序中。另一个类似的增强交互式环境是[bpython](https://www.bpython-interpreter.org/)。

