---
layout: default
title: Junit使用心得
---

#安装
- 把hamcrest-core-1.3.jar和junit-4.12.jar两个包下载到指定目录即可，如D:\jar。

#使用方法
- 如下代码是junit官网上的示例代码，新建一个FooTest.java文件，并把如下代码复制到文件中，并保存。
<pre class="prettyprint" id="java">
package com.example.foo;

import static org.junit.Assert.assertEquals;

import org.junit.Test;
import org.junit.Ignore;
import org.junit.runner.RunWith;
import org.junit.runners.JUnit4;

/**
 * Tests for {@link Foo}.
 *
 * @author user@example.com (John Doe)
 */
public class FooTest {

    @Test
    public void thisAlwaysPasses() {

    }

    @Test
    @Ignore
    public void thisIsIgnored() {
    }
}
</pre>
- 在cmd中输入java -cp D:\jar\junit-4.12.jar;.;D:\jar\hamcrest-core-1.3.jar org.junit.runner.JUnitCore FooTest
<pre class="prettyprint" id="java">
JUnit version 4.12
I.
Time: 0.004

OK (1 test)
</pre>