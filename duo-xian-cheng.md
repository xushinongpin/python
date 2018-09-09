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



