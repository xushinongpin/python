该logging模块提供功能齐全且灵活的记录系统。最简单的是，日志消息被发送到文件或sys.stderr：

```
>>> import logging
>>> logging.debug('Debugging information')
>>> logging.info('Informational message')
>>> logging.warning('Warning:config file %s not found', 'server.conf')
WARNING:root:Warning:config file server.conf not found
>>> logging.error('Error occurred')
ERROR:root:Error occurred
>>> logging.critical('Critical error -- shutting down')
CRITICAL:root:Critical error -- shutting down
>>>
```

默认情况下，信息和调试消息被抑制，输出发送到标准错误。其他输出选项包括通过电子邮件，数据报，套接字或HTTP服务器路由消息。：新过滤器可根据消息优先级来选择不同的路由DEBUG， INFO，WARNING，ERROR，和CRITICAL。

日志记录系统可以直接从Python配置，也可以从用户可编辑的配置文件加载，以便自定义日志记录而无需更改应用程序。

