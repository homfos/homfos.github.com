---
layout: default
title: Junit使用心得
---
#单元测试
- 单元测试能保证代码按照指定的方式运行，完整的单元测试能保证代码在后续的功能增加及bug修复中不影响既有功能，比较到的测试覆盖率能大大减少开发中的手动测试
- 一个单元测试的目标一般是针对一个类或者其中的几个方法。不是一个类中所有的方法都需要测试，像setter或者getter这种功能非常简单的方法可以无需写测试。单元测试主要针对业务中比较重要或者比较复杂的地方
- 测试代码一般和业务代码分开，通常把测试代码放在单独的工程中或者单独的目录中
#Junit安装
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

#测试代码命名
- 测试类的命名可采用被测试的类名+Test，如MyClassTest，MySecondClassTest
- 在测试方法名中加入should，如multiplicationOfZeroIntegersShouldReturnZero，menuShouldGetActive

#从命令行中执行执行测试
从命令行执行代码需要把JUnit的jar包库的位置指定到classpath中
<pre class="prettyprint" id="java">
package de.vogella.junit.first;

import org.junit.runner.JUnitCore;
import org.junit.runner.Result;
import org.junit.runner.notification.Failure;

public class MyTestRunner {
  public static void main(String[] args) {
    Result result = JUnitCore.runClasses(MyClassTest.class);
    for (Failure failure : result.getFailures()) {
      System.out.println(failure.toString());
    }
  }
} 
</pre>
#JUnit code constructs
##JUnit annotations
<pre class="prettyprint" id="java">
@Test 
public void method()    The @Test annotation identifies a method as a test method.
@Test (expected = Exception.class)		Fails if the method does not throw the named exception.
@Test(timeout=100)		Fails if the method takes longer than 100 milliseconds
@Before 
public void method()	This method is executed before each test. It is used to prepare the test environment (e.g., read input data, initialize the class).
@After 
public void method()	This method is executed after each test. It is used to cleanup the test environment (e.g., delete temporary data, restore defaults). It can also save memory by cleaning up expensive memory structures.
@BeforeClass 
public static void method()	This method is executed once, before the start of all tests. It is used to perform time intensive activities, for example, to connect to a database. Methods marked with this annotation need to be defined as static to work with JUnit.
@AfterClass 
public static void method()	This method is executed once, after all tests have been finished. It is used to perform clean-up activities, for example, to disconnect from a database. Methods annotated with this annotation need to be defined as static to work with JUnit.
@Ignore	Ignores the test method. This is useful when the underlying code has been changed and the test case has not yet been adapted. Or if the execution time of this test is too long to be included.
</pre>

##Assert statements
- fail(String)	Let the method fail. Might be used to check that a certain part of the code is not reached or to have a failing test before the test code is implemented. The String parameter is optional.
- assertTrue([message], boolean condition)	Checks that the boolean condition is true.
- assertFalse([message], boolean condition)	Checks that the boolean condition is false.
- assertEquals([String message], expected, actual)	Tests that two values are the same. Note: for arrays the reference is checked not the content of the arrays.
- assertEquals([String message], expected, actual, tolerance)	Test that float or double values match. The tolerance is the number of decimals which must be the same.
- assertNull([message], object)	Checks that the object is null.
- assertNotNull([message], object)	Checks that the object is not null.
- assertSame([String], expected, actual)	Checks that both variables refer to the same object.
- assertNotSame([String], expected, actual)	Checks that both variables refer to different objects.

##测试执行顺序
JUnit不保证测试代码的执行顺序，编写测试代码不能对测试代码的执行顺序做任何假定