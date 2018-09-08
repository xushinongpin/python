有许多模块可用于访问互联网和处理互联网协议。其中两个最简单的方法是urllib.request从URL检索数据和smtplib发送邮件：

```
>>> from urllib.request import urlopen
>>> with urlopen('http://tycho.usno.navy.mil/cgi-bin/timer.pl') as response:
...     for line in response:
...             line = line.decode('utf-8')  # Decoding the binary data to text.
...             if 'EST' in line or 'EDT' in line:  # look for Eastern Time
...                     print(line)
...


（请注意，第二个示例需要在localhost上运行的邮件服务器。）

>>> import smtplib
>>> server = smtplib.SMTP('localhost')
>>> server.sendmail('soothsayer@example.org', 'jcaesar@example.org',
... """To: jcaesar@example.org
... From: soothsayer@example.org
...
... Beware the Ides of March.
... """)
{}
>>>
>>> server.quit()
(221, b'2.0.0 localhost.localdomain closing connection')
>>>

```



