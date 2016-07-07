#获取nginx的upstream状态
本工具可以配合zabbix监控Tengine的Upstream状态。

格式为exe index [upstream|name|status|rise|fall|type|port]
根据指定的命令行参数获取内容
- 第一个参数必须为数字
- 第二个参数为不区分大小写的文本
- 第三个以及以后的参数会丢弃
##使用方法
二进制文件名				服务器序号	需要查询的内容
get-gengine-upstream	1 			status
根据下面内容，会返回index号为1的status状态，输出结果为“1”（up=1，down=0）。
```json
{"servers": {
  "total": 3,
  "generation": 7,
  "server": [
    {"index": 0, "upstream": "tomcat", "name": "127.0.0.1:7070", "status": "up", "rise": 13154, "fall": 0, "type": "tcp", "port": 0},
    {"index": 1, "upstream": "tomcat", "name": "127.0.0.1:9090", "status": "up", "rise": 13166, "fall": 0, "type": "tcp", "port": 0},
    {"index": 2, "upstream": "tomcat", "name": "127.0.0.1:11010", "status": "up", "rise": 19342, "fall": 0, "type": "tcp", "port": 0}
  ]
}}
```

##Nginx监控url配置
需要在编译后的目录内放置url.conf文本文件。
目前只能一行，写http地址。
也不能有空白行。


##二进制文件
已经包含了编译后的linux64和Windows64版本。
- get-tengine-upstream
- get-tengine-upstream.exe
