## 使用pip管理包

您可以使用名为pip的程序安装，升级和删除软件包 。默认情况下，pip将从Python包索引&lt; [https://pypi.org](https://pypi.org) &gt; 安装包。您可以在Web浏览器中浏览Python Package Index，也可以使用pip有限的搜索功能：

```
[root@localhost python]# pip search astronomy
gastropy (0.0dev)        - (g)astronomy
astro-scripts (0.4.0)    - Small scripts for astronomy
n2-tools (0.0.18)        - tools for astronomy data
skyfield (1.7)           - Elegant astronomy for Python
acalib (0.1.3)           - Advanced Computing for Astronomy Library
codex-africanus (0.1.2)  - Radio Astronomy Building Blocks
gary (0.1a)              - Galactic astronomy and gravitational dynamics.
hips (0.2)               - Python astronomy package for HiPS
numina (0.17.3)          - Astronomy data reduction library
palpy (1.8.1)            - PAL -- A Positional Astronomy Library
sinistra (0.3.3)         - A collection of astronomy related tools.
astropy (3.0.4)          - Community-developed python astronomy tools
astrotoyz (0.1.4)        - Astronomy tools built on the Toyz framework
fidia (0.4rc1)           - Format Independent Data Interface for Astronomy
gammapy (0.7)            - A Python package for gamma-ray astronomy
mclearn (0.1.6)          - Active learning algorithms with application in astronomy.
PyAstronomy (0.13.0)     - A collection of astronomy related tools for Python.
pyastroschema (0.5.4)    - Standardized specifications for astronomy and astrophysics data.
starry (0.1.2)           - Analytic occultation light curves for astronomy.
astrodbkit (0.6.6)       - Astronomy database management using SQL and Python
astroML (0.3)            - tools for machine learning and data mining in Astronomy
astroobs (1.4.5)         - Provides astronomy ephemeris to plan telescope observations
DDFacet (0.3.4.1)        - Facet-based radio astronomy continuum imager
python-casacore (2.2.1)  - A wrapper around CASACORE, the radio astronomy library
pyzpace (0.0)            - Zach Pace's astronomy-related python tools
vaex-astro (0.2.0)       - Astronomy related transformations and FITS file support
astrocats (0.3.37)       - Package for downloading, analyzing, and constructing open astronomy catalogs.
cadcdata (1.2.3)         - Client for accessing data at the Canadian Astronomy Data Centre
novas (3.1.1.4)          - The United States Naval Observatory NOVAS astronomy library
simspeclib (2.3.0.3)     - SimSpec library. SIMplified SPECtrum reduction package for astronomy.
simspec-lib (2.3.4.1)    - SimSpec library. SIMplified SPECtrum reduction package for astronomy.
astrobase (0.3.18)       - Python modules and scripts useful for variable star work in astronomy.
astromodels (0.5.1)      - Astromodels contains models to be used in likelihood or Bayesian analysis in astronomy
cygrid (0.9.8)           - Cygrid is a cython-powered convolution-based gridding module for astronomy
f311 (18.3.1.0)          - Astronomy-related API, command-line tools, and windowed applications
simspec (1.8.3)          - User interface for SimSpec. SIMplified SPECtrum reduction package for astronomy.
SWHT (0.1.2)             - Spherical Wave Harmonic Transform for radio astronomy visibility data
nmmn (0.8.4)             - Miscellaneous methods for astronomy, dealing with arrays, statistical distributions and computing goodness-of-fit
Barak (0.3.2)            - A set of astronomy-related routines for generating Voigt profiles from atomic data, reading and writing data, working with SEDs, passbands and dust extinction laws.
You are using pip version 9.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
[root@localhost python]#
```

pip有许多子命令：“搜索”，“安装”，“卸载”，“冻结”等。（有关完整文档，请参阅[安装Python](https://docs.python.org/3/installing/index.html#installing-index)模块指南pip。）

您可以通过指定包的名称来安装最新版本的包：

```
[root@localhost python]# pip install novas
Collecting novas
  Downloading https://files.pythonhosted.org/packages/7b/a3/b4fcb24a9b99f7f6dff371a1e5af96defe08a52c2e44909acb45424ee311/novas-3.1.1.4.tar.gz (139kB)
    100% |████████████████████████████████| 143kB 430kB/s
Installing collected packages: novas
  Running setup.py install for novas ... done
Successfully installed novas-3.1.1.4
You are using pip version 9.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
[root@localhost python]#
```

您还可以通过提供包名称后跟==以及版本号来安装特定版本的包：

```
[root@localhost python]# pip install requests==2.6.0
Collecting requests==2.6.0
  Downloading https://files.pythonhosted.org/packages/73/63/b0729be549494a3e31316437053bc4e0a8bb71a07a6ee6059434b8f1cd5f/requests-2.6.0-py2.py3-none-any.whl (469kB)
    100% |████████████████████████████████| 471kB 1.4MB/s
Installing collected packages: requests
Successfully installed requests-2.6.0
You are using pip version 9.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
[root@localhost python]#
```

如果重新运行此命令，pip将注意到已安装所请求的版本并且不执行任何操作。您可以提供不同的版本号来获取该版本，也可以运行以将软件包升级到最新版本：pip install --upgrade

```
pip install --upgrade requests
Collecting requests
  Downloading https://files.pythonhosted.org/packages/65/47/7e02164a2a3db50ed6d8a6ab1d6d60b69c4c3fdf57a284257925dfc12bda/requests-2.19.1-py2.py3-none-any.whl (91kB)
    100% |████████████████████████████████| 92kB 1.3MB/s
Collecting chardet<3.1.0,>=3.0.2 (from requests)
  Downloading https://files.pythonhosted.org/packages/bc/a9/01ffebfb562e4274b6487b4bb1ddec7ca55ec7510b22e4c51f14098443b8/chardet-3.0.4-py2.py3-none-any.whl (133kB)
    100% |████████████████████████████████| 143kB 2.0MB/s
Collecting idna<2.8,>=2.5 (from requests)
  Downloading https://files.pythonhosted.org/packages/4b/2a/0276479a4b3caeb8a8c1af2f8e4355746a97fab05a372e4a2c6a6b876165/idna-2.7-py2.py3-none-any.whl (58kB)
    100% |████████████████████████████████| 61kB 2.0MB/s
Collecting urllib3<1.24,>=1.21.1 (from requests)
  Downloading https://files.pythonhosted.org/packages/bd/c9/6fdd990019071a4a32a5e7cb78a1d92c53851ef4f56f62a3486e6a7d8ffb/urllib3-1.23-py2.py3-none-any.whl (133kB)
    100% |████████████████████████████████| 143kB 1.4MB/s
Collecting certifi>=2017.4.17 (from requests)
  Downloading https://files.pythonhosted.org/packages/df/f7/04fee6ac349e915b82171f8e23cee63644d83663b34c539f7a09aed18f9e/certifi-2018.8.24-py2.py3-none-any.whl (147kB)
    100% |████████████████████████████████| 153kB 2.6MB/s
Installing collected packages: chardet, idna, urllib3, certifi, requests
  Found existing installation: requests 2.6.0
    Uninstalling requests-2.6.0:
      Successfully uninstalled requests-2.6.0
Successfully installed certifi-2018.8.24 chardet-3.0.4 idna-2.7 requests-2.19.1 urllib3-1.23
You are using pip version 9.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
[root@localhost python]#
```

pip uninstall 后跟一个或多个包名称将从虚拟环境中删除包。

pip show 将显示有关特定包的信息：

```
[root@localhost python]# pip show requests
Name: requests
Version: 2.19.1
Summary: Python HTTP for Humans.
Home-page: http://python-requests.org
Author: Kenneth Reitz
Author-email: me@kennethreitz.org
License: Apache 2.0
Location: /www/wwwroot/python/tutorial-env/lib/python3.7/site-packages
Requires: idna, urllib3, chardet, certifi
You are using pip version 9.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
[root@localhost python]#
```

pip list 将显示虚拟环境中安装的所有软件包：

```
[root@localhost python]# pip list
DEPRECATION: The default format will switch to columns in the future. You can use --format=(legacy|columns) (or define a format=(legacy|columns) in your pip.conf under the [list] section) to disable this warning.
certifi (2018.8.24)
chardet (3.0.4)
idna (2.7)
novas (3.1.1.4)
pip (9.0.1)
requests (2.19.1)
setuptools (28.8.0)
urllib3 (1.23)
You are using pip version 9.0.1, however version 18.0 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
[root@localhost python]#

```



