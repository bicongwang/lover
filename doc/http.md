## 复制两段HTTP协议报文，要求分别为请求报文和响应报文

请求报文举例：  
GET /hello.txt HTTP/1.1  
User-Agent: curl/7.16.3 libcurl/7.16.3 OpenSSL/0.9.7l zlib/1.2.3  
Host: www.example.com  
Accept-Language: en, mi  

响应报文举例：  
HTTP/1.1 200 OK  
Date: Mon, 27 Jul 2009 12:28:53 GMT  
Server: Apache  
Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT  
ETag: "34aa387-d-1568eb00"  
Accept-Ranges: bytes  
Content-Length: 51  
Vary: Accept-Encoding  
Content-Type: text/plain  


## 请求报文的HTTP方法是什么，请对比两大HTTP方法的不同：GET和POST

根据HTTP标准，HTTP请求可以使用多种请求方法。  
HTTP1.0定义了三种请求方法： GET, POST 和 HEAD方法。  
HTTP1.1新增了五种请求方法：OPTIONS, PUT, DELETE, TRACE 和 CONNECT 方法。  

GET：请求指定的页面信息，并返回实体主体。  
POST：向指定资源提交数据进行处理请求（例如提交表单或者上传文件）。数据被包含在请求体中。POST请求可能会导致新的资源的建立和/或已有资源的修改。  


## 响应报文的HTTP状态码是什么，请简述1~5xx系列状态的作用，并从中选出你最有眼缘的两个status code，说明他们的作用

当浏览者访问一个网页时，浏览者的浏览器会向网页所在服务器发出请求。当浏览器接收并显示网页前，此网页所在的服务器会返回一个包含HTTP状态码的信息头（server header）用以响应浏览器的请求。  
HTTP状态码由三个十进制数字组成，第一个十进制数字定义了状态码的类型，后两个数字没有分类的作用。  
HTTP状态码共分为5种类型：
> 1** : 信息，服务器收到请求，需要请求者继续执行操作  
> 2** : 成功，操作被成功接收并处理  
> 3** : 重定向，需要进一步的操作以完成请求  
> 4** : 客户端错误，请求包含语法错误或无法完成请求  
> 5** : 服务器错误，服务器在处理请求的过程中发生了错误  

举例：  
200：请求成功。一般用于GET与POST请求  
403：服务器理解请求客户端的请求，但是拒绝执行此请求  


## 请求报文和响应的报文的首部字段（headers）各是哪一段，从中选出你最有眼缘的两个字段，说明他们的作用和他们可能的取值与取值的含义
#### 客户端发送一个HTTP请求到服务器的请求消息包括以下格式：请求行（request line）、请求头部（header）、空行和请求数据四个部分组成，下图给出了请求报文的一般格式。
![](http://www.runoob.com/wp-content/uploads/2013/11/2012072810301161.png)
#### HTTP响应也由四个部分组成，分别是：状态行、消息报头、空行和响应正文。
![](http://www.runoob.com/wp-content/uploads/2013/11/httpmessage.jpg)

请求报文中的“请求行”由请求方法，URL和协议版本组成，第一题所举例子中
> GET /hello.txt HTTP/1.1  即为请求行，表示此请求报文为GET请求，/hello.txt为要访问资源，使用的是HTTP1.1版本。  

响应报文中的“消息报头”，用来说明客户端要使用的一些附加信息，上面所举例子中  

> Date: Mon, 27 Jul 2009 12:28:53 GMT  
> Server: Apache  
> Last-Modified: Wed, 22 Jul 2009 19:15:56 GMT  
> ETag: "34aa387-d-1568eb00"  
> Accept-Ranges: bytes  
> Content-Length: 51  
> Vary: Accept-Encoding  
> Content-Type: text/plain  

即为消息报头，  
Date:生成响应的日期和时间；  
Content-Type:指定了MIME类型的HTML(text/html)；  
charset:编码类型是ISO-8859-1;  
Content-Length:用于描述HTTP消息实体的传输长度。
