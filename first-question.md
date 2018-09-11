# linux上python安装方法

libffi-devel 必装

```
yum -y groupinstall "Development tools"
yum -y install zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel libffi-devel

获取 python3.7 包
wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0a1.tar.xz
解压
tar -xvJf  Python-3.7.0a1.tar.xz
配置安装目录并安装
cd Python-3.7.0a1
./configure --prefix=/usr/local/bin/python3
sudo make
make install
创建软链接
ln -s /usr/local/bin/python3/bin/python3 /usr/bin/python3
ln -s /usr/local/bin/python3/bin/pip3 /usr/bin/pip3
执行能进去 安装成功
python3
```

# **window上安装**

[下载包](https://www.python.org/ftp/python/3.7.0/python-3.7.0.exe)

配置环境变量 path【系统-更改设置-高级-环境变量】，添加python路径 【C:\Users\Administrator\AppData\Local\Programs\Python\Python37-32  具体看您安装目录】

