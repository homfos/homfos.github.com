---
layout: default
title: http学习笔记
---

#HTTP(超文本传输协议）
***
##get和post的区别
用来传输html
两种最常用的两种请求：get和post，二者的区别如下：

- get方法中字符总长度有最大数限制，post无最大限制
- get方法发送的数据显示在URL中(追加在请求URL的后面，以？开头，如有多个参数以&分割），所有用户可以bookmark
- post方法中，用户参数信息显示在消息体，非在消息头
- post请求有消息体，而get请求无消息体
- post请求非idempotent,要自己处理同一个请求被重复提交的错误情况
- 如果一个html的form没有指明method=post，默认的提交方法是get

#未完待续