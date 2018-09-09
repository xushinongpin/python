## 多线程

线程化是一种解耦非顺序依赖的任务的技术。线程可用于提高接受用户输入的应用程序的响应能力，而其他任务在后台运行。相关用例是与另一个线程中的计算并行运行I / O.

以下代码显示了threading当主程序继续运行时，高级模块如何在后台运行任务：

```
>>> import threading, zipfile
>>> class AsyncZip(threading.Thread):
...     def __init__(self, infile, outfile):
...             threading.Thread.__init__(self)
...             self.infile = infile
...             self.outfile = outfile
...     def run(self):
...             f = zipfile.ZipFile(self.outfile, 'w', zipfile.ZIP_DEFLATED)
...             f.write(self.infile)
...             f.close()
...             print('Finished background zip of:', self.infile)
...
>>> background = AsyncZip('mydata.txt', 'myarchive.zip')
>>> background.start()
>>> Finished background zip of: mydata.txt
print('The main program continues to run in foreground.')
The main program continues to run in foreground.
>>> background.join()    # Wait for the background task to finish
>>> print('Main program waited until background was done.')
Main program waited until background was done.
>>>
```

多线程应用程序的主要挑战是协调共享数据或其他资源的线程。为此，线程模块提供了许多同步原语，包括锁，事件，条件变量和信号量。

虽然这些工具功能强大，但较小的设计错误可能导致难以重现的问题。因此，任务协调的首选方法是将对资源的所有访问集中在一个线程中，然后使用该 queue模块为来自其他线程的请求提供该线程。使用Queue对象进行线程间通信和协调的应用程序更易于设计，更易读，更可靠。

