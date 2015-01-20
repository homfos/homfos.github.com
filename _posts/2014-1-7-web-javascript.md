---
layout: default
title: javascript
---
#javascript简介
- javascript是一个面向object的语言
- javascript没有class。class的功能通过object prototype提供
- javascript不用处理输入输出。宿主环境提供和对外交流的机制
- javascript的function为object
#javascript基本类型
- Number
- String
- Boolean(false, 0, the empty string (""), NaN, null, and undefined all become false;其它情况为true)
- Symbol
- Object
Function
Array
Date
RegExp
- Null
- Undefined(actually a constant)

可以用undefined去查看一个变量是否有值。如:
<pre class="prettyprint" id="javascript">
var input;
if(input === undefined){
  doThis();
} else {
  doThat();
}
</pre>
在真值判断时undefined表现为false，如下面myArray中的数组元素没有定义，所有myFunction()会执行
<pre class="prettyprint" id="javascript">
var myArray = new Array();
if (!myArray[0]) myFunction();
</pre>
在需要数值的上下文中undefined会被转化为NaN，而null会被转化为0
<pre class="prettyprint" id="javascript">
var a;
a + 2 = NaN

var n = null;
console.log(n * 32); // Will log 0 to the console
</pre>

#数据类型转换
当字符串和数字相加时，数字自动被转化为字符串。但当不是+时，数字不被转化为字符串。字符串通过parseInt() and parseFloat()转换为数字,还有一种把字符串转成数字的方式是用+操作符
<pre class="prettyprint" id="javascript">
x = "The answer is " + 42 // "The answer is 42"
y = 42 + " is the answer" // "42 is the answer"

"37" - 7 // 30
"37" + 7 // "377"

(+"1.1") + (+"1.1") = 2.2 
</pre>

#变量范围
blocks do not have scope; only functions have scope
当一个变量没在任何一个函数内部声明时，变量为全局变量，其它的变量都为局部变量。
JavaScript does not have block statement scope; rather, a variable declared within a block is local to the function (or global scope) that the block resides within. For example the following code will log 5, because the scope of x is the function (or global context) within which x is declared, not the block, which in this case is an if statement.
<pre class="prettyprint" id="javascript">
if (true) {
  var x = 5;
}
console.log(x);
</pre>

Another unusual thing about variables in JavaScript is that you can refer to a variable declared later, without getting an exception. This concept is known as hoisting; variables in JavaScript are in a sense "hoisted" or lifted to the top of the function or statement. However, variables that aren't initialized yet will return a value of undefined.
<pre class="prettyprint" id="javascript">
/**
 * Example 1
 */
console.log(x === undefined); // logs "true"
var x = 3;

/**
 * Example 2
 */
// will return a value of undefined
var myvar = "my value";
 
(function() {
  console.log(myvar); // undefined
  var myvar = "local value";
})();
</pre>
##比较
The double-equals operator performs type coercion if you give it different types
<pre class="prettyprint" id="javascript">
> "dog" == "dog"
true
> 1 == true
true

> 1 === true
false
> true === true
true
</pre>