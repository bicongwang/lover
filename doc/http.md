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


## 为什么说HTTP协议是无状态的

HTTP协议是无状态协议。  
无状态是指协议对于事务处理没有记忆能力。缺少状态意味着如果后续处理需要前面的信息，则它必须重传，这样可能导致每次连接传送的数据量增大。另一方面，在服务器不需要先前信息时它的应答就较快。

## 无状态的HTTP协议下如何通过Cookie/Session来完成用户认证

Cookie是通过客户端保持状态的解决方案。  
从定义上来说，Cookie就是由服务器发给客户端的特殊信息，而这些信息以文本文件的方式存放在客户端，然后客户端每次向服务器发送请求的时候都会带上这些特殊的信息。  
当用户使用浏览器访问一个支持Cookie的网站的时候，用户会提供包括用户名在内的个人信息并且提交至服务器；接着，服务器在向客户端回传相应的超文本的同时也会发回这些个人信息，当然这些信息并不是存放在HTTP响应体（Response Body）中的，而是存放于HTTP响应头（Response Header）；当客户端浏览器接收到来自服务器的响应之后，浏览器会将这些信息存放在一个统一的位置，对于Windows操作系统而言，我们可以从： [系统盘]:\Documents and Settings\[用户名]\Cookies目录中找到存储的Cookie；自此，客户端再向服务器发送请求的时候，都会把相应的Cookie再次发回至服务器。而这次，Cookie信息则存放在HTTP请求头（Request Header）了。  

与Cookie相对的一个解决方案是Session，它是通过服务器来保持状态的。  
由于Session这个词汇包含的语义很多，因此需要在这里明确一下 Session的含义。首先，我们通常都会把Session翻译成会话，因此我们可以把客户端浏览器与服务器之间一系列交互的动作称为一个 Session。从这个语义出发，我们会提到Session持续的时间，会提到在Session过程中进行了什么操作等等；其次，Session指的是服务器端为客户端所开辟的存储空间，在其中保存的信息就是用于保持状态。从这个语义出发，我们则会提到往Session中存放什么内容，如何根据键值从 Session中获取匹配的内容等。  
要使用Session，第一步当然是创建Session了。那么Session在何时创建呢？当然还是在服务器端程序运行的过程中创建的，不同语言实现的应用程序有不同创建Session的方法，而在Java中是通过调用HttpServletRequest的getSession方法（使用true作为参数）创建的。在创建了Session的同时，服务器会为该Session生成唯一的Session id，而这个Session id在随后的请求中会被用来重新获得已经创建的Session；在Session被创建之后，就可以调用Session相关的方法往Session中增加内容了，而这些内容只会保存在服务器中，发到客户端的只有Session id；当客户端再次发送请求的时候，会将这个Session id带上，服务器接受到请求之后就会依据Session id找到相应的Session，从而再次使用之。正是这样一个过程，用户的状态也就得以保持了。  

## 请介绍Basic Authentication和OAuth2用户认证机制，要求说明其在HTTP协议报文中的位置

当用访问需要登录验证的页面时，浏览器会自动弹出一个对话框，要求输入用户名/密码，输入正确后可以正常访问。  
在这种方式中，浏览器会把用户名和密码通过BASE64编码在HTTP HEAD 里面  
> Authorization: Basic QWxhZGRpbjpPcGVuU2VzYW1l  

服务器端解析之后做身份验证，并给客户端返回  

> WWW-Authenticate: Basic realm="User Visible Realm"

客户端每次请求都会携带用户名密码，需要通过HTTPs来保证安全。另外客户端需要缓存用户名和密码，以保证不必每次请求都要用户重新输入用户名和密码，通常浏览器会在本地保存10分钟左右的时间，超过之后需要用户再次输入用户名密码。  
这是基于HTTP协议的比较传统的身份验证方案，现在已经很少使用。

OAuth2的基本流程为：

1. 第三方应用请求用户授权
2. 用户同意授权，并返回一个凭证（code）
3. 第三方应用通过第二步的凭证（code）向授权服务器请求授权
4. 授权服务器验证凭证（code）通过后，同意授权，并返回一个资源访问的凭证（Access Token）。
5. 第三方应用通过第四步的凭证（Access Token）向资源服务器请求相关资源。
6. 资源服务器验证凭证（Access Token）通过后，将第三方应用请求的资源返回。
