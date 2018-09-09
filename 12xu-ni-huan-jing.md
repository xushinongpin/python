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



