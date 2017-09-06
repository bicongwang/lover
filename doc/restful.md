## Restful API是一种基于HTTP协议的API设计风格，请你说出其他几种API设计风格（说出两三个名词即可，无须介绍）
```
 AngularJS API   
 jQuery UI API  
```
以上答案不对，正确答案还是没找到。

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

- URL定位资源用HTTP动词（GET POST DELETE）描述操作
- 使URL回归对资源的抽象

```
王老师有话说：

1. URL本身的意义，你是否发现URL跟系统中文件路径有点类似，系统中文件路径可能指某个目录或者某个文件，而URL的名字即是统一资源定位符，实际上他们都应该是对文件系统的抽象。Restful作为一种简约的设计风格，让URL只能是名词，其实就是让URL回归了自己的本意，在Restful API中URL就是对资源的抽象。
2. 虽然你认为/api/getBooks这样的设计，把get和Books连接起来， 所以更加简洁。但是实际上，你有没有发现，这种设计完整来看是get /api/getBooks，而Restful API是get /api/books，此时你有没有发现，这样的设计并不简洁，反而多余。
3. 之前让你大概了解了HTTP协议，之所以最开始只让你学习get和post方法，是因为如果自己任性设计API，根本用不上那么多method，因为url本身是无限空间的，甚至我可以只用get方法，参照我在该题中写的设计，用/api/getBook /api/addBook /api/deleteBook /api/updateBook，是不是只用了get方法就完成了
restful api需要用四个方法完成的任务，但是这里要注意的是，restful api设计中只有一个url : /api/book。在这个例子中你就能发现，restful api为什么简约，实际上他是让method和url各司其职。url就是一个物品，而method就是能对这个物品进行的操作，而不像题中的设计，只有行为的资源，而无单纯的资源的概念。
4. 虽然我以上都是吹捧Restful API，但是由于Restful API对API抽象程度要求高，要求我们必须对每个API都抽象出资源URL和行为Method这两个概念，所以在复杂系统的设计中，容易增加设计成本，甚至这些略显苛刻的条件并不能满足实际需求，这样我们就可能需要不严格按照Restful API的设计。
5. 第4点我只是依照惯例，不能强吹一个技术去贬低其他技术。反正现在Restful API是最流行的设计风格，别的风格再吹也没卵用 🐶 设计不好只能说太菜 🐶
```
