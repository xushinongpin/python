该struct模块提供pack\(\)和 unpack\(\)使用可变长度二进制记录格式的功能。以下示例显示如何在不使用zipfile模块的情况下循环ZIP文件中的标头信息 。打包代码"H"并分别"I"表示两个和四个字节的无符号数字。在"&lt;"表明他们是标准的尺寸和little-endian字节顺序：

```
>>> import struct
>>> with open('myfile.zip', 'rb') as f:
...     data = f.read()
...     start = 0
...     for i in range(3):
...             start += 14
...             fields = struct.unpack('<IIIHH', data[start:start+16])
...             crc32, comp_size, uncomp_size, filenamesize, extra_size = fields
...             start += 16
...             filename = data[start:start+filenamesize]
...             start += filenamesize
...             extra = data[start:start+extra_size]
...             print(filename, hex(crc32), comp_size, uncomp_size)
...             start += extra_size + comp_size     # skip to the next header
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
FileNotFoundError: [Errno 2] No such file or directory: 'myfile.zip'
>>>
有该文件就如下显示
b'qaz.txt' 0xcc57e2ce 271151 2399493
b'$\x00\x00\x00\x00\x00\x00\x00 \x00\x00\x00\x00\x00\x00\x00dev_500w.sql\n\x00 \x00\x00\x00\x00\x00' 0xe2ce4d28 590335063 2634350596
Traceback (most recent call last):
  File "<stdin>", line 6, in <module>
struct.error: unpack requires a buffer of 16 bytes
>>>

```



