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



