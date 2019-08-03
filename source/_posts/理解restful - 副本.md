---
title: 理解RESTful API
date: 2019-08-02 13:55:01
tags: Restful
categories: 
- Restful
---



 服务端根据不同的请求方式，可以做不同的处理，同时，根据不同的请求，还可以设计出不同风格的应用程序接口，这就引出了Representational State Transfer，英文缩写就是REST，中文意思是表述性状态转移（和没翻译差不多），可以理解为客户端和服务端的交互形式。而符合这种交互形式的接口设计，就被叫做RESTful API。这种风格有如下特点：

##### 1. url 使用名词而不使用动词
	eg: /getlist/ #这样是不符合restful风格的
		正确的应该是 /list/
##### 2.GET用于查询，PUT、POST、DELETE用于修改
##### 3.使用名词复数不使用单数
	eg: /student/ 应该是 /students/
##### 4.在HTTP请求的head体里定义序列化类型
  	eg: Content-Type:application/json
##### 5.请求的集合应设定好过滤条件、排序、字段、分页
	eg：/students?page=1&size=10
##### 6.接口要版本化

	eg：/api/v1/students
##### 7.要有HTTP状态码
##### 8.允许重写HTTP请求方法
##### 9.aaaa
