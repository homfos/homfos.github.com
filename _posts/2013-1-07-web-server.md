---
layout: default
title: Web Server
---

#What are web server, application server and web container?

A web server responsibility is to handler HTTP requests from client browsers and respond with HTML response. A web server understands HTTP language and runs on HTTP protocol.
Apache Web Server is kind of a web server and then we have specific containers that can execute servlets and JSPs known as servlet container, for example Tomcat.
Application Servers provide additional features such as Enterprise JavaBeans support, JMS Messaging support, Transaction Management etc. So we can say that Application server is a web server with additional functionalities to help developers with enterprise applications.

Web container, specially in java, should be refer to servlet container. A servlet container is the component of a web server that interacts with java servlets. A web container is responsible for managing the life-cycle of servlets, mapping a URL to a particular servlet and ensuring that the URL requester has the correct access rights and many more such services. Basically, putting together all above facts, servlet container is the runtime environment where your servlet run and it’s life cycle is maintained.

#What are Servlets? How they help?

In java, servlets enable you to write server side components which help in generating dynamic content, based on request. Factually, Servlet is an interface defined in javax.servlet package. It declares three essential methods for the life cycle of a servlet – init(), service(), and destroy(). They are implemented by every servlet(either defined in SDK or user-defined) and are invoked at specific times by the server during it’s life cycle.

Servlet classes are loaded to container by it’s class loader dynamically either through lazy-loading or eager loading. Each request is in its own thread, and a servlet object can serve multiple threads at the same time. When it is no longer being used, it is garbage collected by JVM.

#Which HTTP method is non-idempotent?
A HTTP method is said to be idempotent if it returns the same result every time. HTTP methods GET, PUT, DELETE, HEAD, and OPTIONS are idempotent method and we should implement our application to make sure these methods always return same result. HTTP method POST is non-idempotent method and we should use post method when implementing something that changes with every request.

For example, to access an HTML page or image, we should use GET because it will always return the same object but if we have to save customer information to database, we should use POST method. Idempotent methods are also known as safe methods and we don’t care about the repetitive request from the client for safe methods.

#Which HTTP method is non-idempotent?

A HTTP method is said to be idempotent if it returns the same result every time. HTTP methods GET, PUT, DELETE, HEAD, and OPTIONS are idempotent method and we should implement our application to make sure these methods always return same result. HTTP method POST is non-idempotent method and we should use post method when implementing something that changes with every request.

For example, to access an HTML page or image, we should use GET because it will always return the same object but if we have to save customer information to database, we should use POST method. Idempotent methods are also known as safe methods and we don’t care about the repetitive request from the client for safe methods.