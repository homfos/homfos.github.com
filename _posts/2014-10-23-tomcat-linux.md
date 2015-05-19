---
layout: default
title: Linux下Tomcat端口配置为80时服务起不来的问题
---
#问题
在CentOS下修改把tomcat的默认端口修改为80时服务起不来，通过netstat -an 80|grep 80命令发现端口没有打开。于是查看了tomcat的日志，有如下报错：
![](http://i.imgur.com/TqF7t6Z.png)
#原因
在linux中1024一下的端口号为特权端口，必须需要root权限才能绑定。
#解决方法
这个问题有很多种解决方法，我采用了一个相对简单的方式，即用iptables进行本地端口转发。在系统中执行如下命令即可：
<pre class="prettyprint" id="bash">
iptables -A INPUT -i eth0 -p tcp --dport 80 -j ACCEPT
iptables -A INPUT -i eth0 -p tcp --dport 8080 -j ACCEPT
iptables -A PREROUTING -t nat -i eth0 -p tcp --dport 80 -j REDIRECT --to-port 8080
</pre>