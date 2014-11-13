---
layout: default
title: Centos环境下用Hudson及SVN搭建持续集成环境
---

#Hudson安装
---
1. Install Java runtime
---
 yum install java

2. Add Hudson repository URL to package management
---
wget -O /etc/yum.repos.d/hudson.repo http://hudson-ci.org/redhat/hudson.repo

---
3. Install Hudson
yum install hudson
---

4. Starting and Stopping Hudson 
sudo service hudson stop
sudo service hudson start
---

---
#Hudson配置
- 在http://10.25.79.176:8080/securityManager/的页面中enable security,在Access Control 选择Hudson's own user database
- 在http://10.25.79.176:8080/job/(JOB_NAME)/configure页面下勾选Trigger builds remotely，在Authentication Token中输入cd

#SVN post hook配置
在svn的工程目录下的hooks的目录中，通过post-commit.tmpl模板复制出一个post-commit，然后执行chmod a+x post-commit给其增加可执行权限。然后在post-commit末尾添加如下内容：
<pre class="prettyprint" id="bash">
/usr/bin/wget \
  --header "Content-Type:text/plain;charset=UTF-8" \
  --post-data "`svnlook changed --revision $REV $REPOS`" \
  --output-document "-" \
  --timeout=2 \
http://10.25.79.176:8080/job/equipment_maintain/build?token=cd

</pre>