安装命令

```
pip install Scrapy  // pip 是你软命名，你命名什么就写什么
安装完后在python的bin目录可以找到
创建软链接 ln -s /usr/local/bin/python3/bin/scrapy /usr/bin/scrapy
```

无法遇到ssl安装时： 安装 openssl

```
 yum install -y openssl-devel
 ./configure --prefix='/usr/local/bin/python3' --with-ssl //进到python目录
```

如果提示pip3不够新

```
可以到 https://pypi.org/project/pip/ 官网下载最新的【进到目录执行 python setup.py install 】
```

进入home目录加别名

```
[root@localhost ~]# vi .bashrc
  # .bashrc

  # User specific aliases and functions

  alias rm='rm -i'
  alias cp='cp -i'
  alias mv='mv -i'
  alias python3='/usr/local/bin/python3/bin/python3.7'
  alias pip3='/usr/local/bin/python3/bin/pip3'
  alias scrapy='/usr/local/bin/python3/bin/scrapy'

  # Source global definitions
  if [ -f /etc/bashrc ]; then
   . /etc/bashrc
  fi

重新启动
  [root@localhost ~]# source .bashrc
```



