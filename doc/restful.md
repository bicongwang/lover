## Restful API是一种基于HTTP协议的API设计风格，请你说出其他几种API设计风格（说出两三个名词即可，无须介绍）
```
 AngularJS API   
 jQuery UI API  
```

## Restful API中HTTP协议的四大方法get post put delete各表示什么

常用的HTTP动词有下面五个（括号里是对应的SQL命令）。  
> GET（SELECT）：从服务器取出资源（一项或多项）。  
> POST（CREATE）：在服务器新建一个资源。  
> PUT（UPDATE）：在服务器更新资源（客户端提供改变后的完整资源）。  
> PATCH（UPDATE）：在服务器更新资源（客户端提供改变的属性）。  
> DELETE（DELETE）：从服务器删除资源。  


## Restful API中URL如何进行设计

1. API与用户的通信协议，总是使用HTTPs协议。  
2. 应该尽量将API部署在专用域名之下。`https://api.example.com`如果确定API很简单，不会有进一步扩展，可以考虑放在主域名下。`https://example.org/api/`  
3. 应该将API的版本号放入URL。
`https://api.example.com/v1/`
另一种做法是，将版本号放在HTTP头信息中，但不如放入URL方便和直观。Github采用这种做法。  
4. 路径又称"终点"（endpoint），表示API的具体网址。
在RESTful架构中，每个网址代表一种资源（resource），所以网址中不能有动词，只能有名词，而且所用的名词往往与数据库的表格名对应。一般来说，数据库中的表都是同种记录的"集合"（collection），所以API中的名词也应该使用复数。  
举例来说，有一个API提供动物园（zoo）的信息，还包括各种动物和雇员的信息，则它的路径应该设计成下面这样。  
```
https://api.example.com/v1/zoos
https://api.example.com/v1/animals
https://api.example.com/v1/employees
```
5. 对于资源的具体操作类型，由HTTP动词表示。客户端通过四个HTTP动词，对服务器端资源进行操作，实现"表现层状态转化"。  
```
GET /zoos：列出所有动物园
POST /zoos：新建一个动物园
GET /zoos/ID：获取某个指定动物园的信息
PUT /zoos/ID：更新某个指定动物园的信息（提供该动物园的全部信息）
PATCH /zoos/ID：更新某个指定动物园的信息（提供该动物园的部分信息）
DELETE /zoos/ID：删除某个动物园
GET /zoos/ID/animals：列出某个指定动物园的所有动物
DELETE /zoos/ID/animals/ID：删除某个指定动物园的指定动物
```


## 为什么/api/getBooks这样的URL PATH不符合Restful API设计风格

在RESTful架构中，每个网址代表一种资源（resource），所以网址中不能有动词，只能有名词，而且所用的名词往往与数据库的表格名对应。  


## 你认为用Restful API改写/api/getBooks后，有什么好处（可以结合对HTTP协议的理解）

URL定位资源用HTTP动词（GET POST DELETE）描述操作。
