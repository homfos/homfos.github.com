---
layout: default
title: linux java环境变量设置
---
#java home的安装路径判断
用在linux下用which java判断java的可执行文件路径

![](http://i.imgur.com/hyvrO0d.png)

在/etc/profile中添加
JAVA_HOME=/usr/lib/jvm/java-1.6.0-openjdk/
PATH=$PATH:$JAVA_HOME
export JAVA_HOME
export PATH