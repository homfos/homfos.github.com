---
layout: default
title: javascript闭包
---
#javascript简介
- javascript是一个面向object的语言
- javascript没有class。class的功能通过object prototype提供
- javascript不用处理输入输出。宿主环境提供和对外交流的机制
- javascript的function为object

#javascript闭包
They have to be used carefully, as what this refers to depends completely on where the function was called, rather than where it was defined.
<pre class="prettyprint" id="javascript">
var name = "The Window";
　　var object = {
　　　　name : "My Object",
　　　　getNameFunc : function(){
　　　　　　return function(){
　　　　　　　　return this.name;
　　　　　　};
　　　　}
　　};
　　alert(object.getNameFunc()());

代码片段二。
　　var name = "The Window";
　　var object = {
　　　　name : "My Object",
　　　　getNameFunc : function(){
　　　　　　var that = this;
　　　　　　return function(){
　　　　　　　　return that.name;
　　　　　　};
　　　　}
　　};
　　alert(object.getNameFunc()());
</pre>
