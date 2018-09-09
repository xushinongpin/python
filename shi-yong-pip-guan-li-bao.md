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



