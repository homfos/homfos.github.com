---
layout: default
title: linux java安装
---
#下载
<pre class="prettyprint" id="java">
# cd /opt/
# wget --no-cookies --no-check-certificate --header \
"Cookie: gpw_e24=http%3A%2F%2Fwww.oracle.com%2F; oraclelicense=accept-\
securebackup-cookie" "http://download.oracle.com/otn-pub/java/jdk/7u75-b13/\
jdk-7u75-linux-i586.tar.gz"
# tar xzvf jdk-7u75-linux-i586.tar.gz
# cd /opt/jdk1.7.0_75/
# alternatives --install /usr/bin/java java /opt/jdk1.7.0_75/bin/java 2
# alternatives --config java
</pre>
#安装
![](http://i.imgur.com/uTGBdxS.png)
<pre class="prettyprint" id="java">
# alternatives --install /usr/bin/jar jar /opt/jdk1.7.0_75/bin/jar 2
# alternatives --install /usr/bin/javac javac /opt/jdk1.7.0_75/bin/javac 2
# alternatives --set jar /opt/jdk1.7.0_75/bin/jar
# alternatives --set javac /opt/jdk1.7.0_75/bin/javac 
# java -version

java version "1.7.0_75"
Java(TM) SE Runtime Environment (build 1.7.0_75-b13)
Java HotSpot(TM) 64-Bit Server VM (build 24.75-b04, mixed mode)
</pre>
#配置环境变量
在/etc/profile中添加
JAVA_HOME=$PATH:/opt/jdk1.7.0_75/bin:/opt/jdk1.7.0_75/jre/bin