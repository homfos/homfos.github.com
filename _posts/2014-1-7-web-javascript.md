---
layout: default
title: javascript
---
#javascript中的5种基本类型
- Numbers
- Logical (Boolean)
- Strings
- null（和NULL不同）
- undefined

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
当字符串和数字相加时，数字自动被转化为字符串。但当不是+时，数字不被转化为字符串。字符串通过parseInt() and parseFloat()转换为数字
<pre class="prettyprint" id="javascript">
x = "The answer is " + 42 // "The answer is 42"
y = 42 + " is the answer" // "42 is the answer"

"37" - 7 // 30
"37" + 7 // "377"
</pre>

#变量范围
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