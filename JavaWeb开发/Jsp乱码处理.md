Jsp 乱码处理
===================


-------------  ---

>1.乱码情况
  
 	当jsp页面第一次被访问到时.jsp引擎将jsp文件翻译成Servlet,
 	此时，如果不明确指定，则翻译引擎在读取jsp文件是将使用utf-8码表，
 	如果当时存jsp时，使用的码表跟读取文件使用码表不一致就会长身乱码。
 	
>2.乱码情况

	在编码时使用ios8859-1，输出中文到浏览器。
	如果没有指定编码服务到格式，浏览器打开会产生乱码。
	
	
-------------
* 解决办法

	在jsp的page指令中有一个属性pageEncoding属性，用来同孩子
	jsp翻译引擎以什么编码读取jsp。只需每次在编码时将
	pageEncoding值设置为当初保存jsp使用的编码，
	就不会出现乱码了。
	
------------
	

```
	<%@ page contentType="text/html;charset=UTF-8" language="java" session="false" isThreadSafe="true" errorPage="error.jsp"
         pageEncoding="utf-8" %>
<html>
<head>
    <title></title>
</head>
<body>
服务器出错了哦。。。
<% int i = 1 / 0;%>
</body>
</html>
```












