# NginxStudy
学习Nginx，了解基本的搭建和使用

# 入门
老规矩，入门第一盘看官方的[入门指南](http://nginx.org/en/docs/beginners_guide.html)。
入门主要讲了几件事：

1. 操作 nginx 程序的基本命令
```
    stop — fast shutdown
    quit — graceful shutdown
    reload — reloading the configuration file
    reopen — reopening the log files
```
比如，更更改设置后重新加载设置，就用命令 `nginx -s reload`，其余以此类推。
2. 配置文件的结构，讲得真是蛮简单。配置文件里分为指令[^directive]和注释。指定有两种，基本指令和块级指令。基本指令由指令名和参数组成，以 ; 结尾；块级指令以`{}`包裹其他命令[^instruction]。包含其他指令的指令又称作上下文，如 events\http\server\location 等，注释以`#`开头。
上下文指令的包含关系为：
```
main {
	events;
	http {
		server {
			location {}
		}
	}
}
```

# Resources
* https://github.com/fcambus/nginx-resources

[^directive]: 英文为*directive*
[^instruction]: 英文为*instruction*