## 创建虚拟环境

用于创建和管理虚拟环境的模块被调用 venv。 venv通常会安装您可用的最新版本的Python。如果您的系统上有多个版本的Python，则可以通过运行python3或任何您想要的版本来选择特定的Python版本。

要创建虚拟环境，请确定要放置它的目录，然后将该venv模块作为带有目录路径的脚本运行：

```
python3 -m venv tutorial-env
```

tutorial-env如果目录不存在，这将创建目录，并在其中创建包含Python解释器，标准库和各种支持文件的副本的目录。

创建虚拟环境后，您可以激活它。

在Windows上，运行：

```
tutorial-env\Scripts\activate.bat
```

在Unix或MacOS上，运行：

```
source tutorial-env/bin/activate
```

（这个脚本是为bash shell编写的。如果你使用 csh或fish shell，你应该使用替代 activate.csh和activate.fish脚本。）

激活虚拟环境将改变shell的提示，以显示您正在使用的虚拟环境，并修改环境，以便运行 python将获得特定版本和Python的安装。例如：

```
>>> getcontext().prec = 36
>>> Decimal(1) / Decimal(7)
Decimal('0.142857142857142857142857142857142857')
>>> exit()
[root@localhost python]# python3 -m venv tutorial-env
[root@localhost python]# source tutorial-env/bin/activate
(tutorial-env) [root@localhost python]# source /www/wwwroot/python/tutorial-env/bin/activate
(tutorial-env) [root@localhost python]# python
Python 3.7.0a1 (default, Aug 11 2018, 03:18:46)
[GCC 4.4.7 20120313 (Red Hat 4.4.7-23)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import sys
>>> sys.path
['', '/usr/local/bin/python3/lib/python37.zip', '/usr/local/bin/python3/lib/python3.7', '/usr/local/bin/python3/lib/python3.7/lib-dynload', '/www/wwwroot/python/tutorial-env/lib/python3.7/site-packages']
>>>

```



