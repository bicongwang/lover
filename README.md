# lover
:heart:

## 目录

[1. 再次熟悉github](#1-再次熟悉github)      
[2. 学习markdown格式](#2-学习markdown格式)                    
[3. 理解HTTP协议](#3-理解http协议)            
[4. HTTP协议的认证机制](#4-http协议的认证机制)          
[5. Restful API](#5-restful-api)                
[6. 初识Ingress](#6-初识ingress)       
[7. Github Restful API](#7-github-restful-api)          
[8. Npm与React环境搭建](#8-npm与react环境搭建)      

## 1. 再次熟悉github

> 2017.8.22       

### 任务步骤     

1. fork本仓库到自己的账号下
2. 将自己的mirror仓库clone到本地电脑上
3. 在本地建立develop分支，并且切换到develop分支（默认是master分支）
4. 在根目录下建立`doc`目录，在该目录里新建`demo.md`文件
5. 将4修改add+commit后，push到自己账号远程仓库的master分支
6. 在自己github账号的mirror仓库里从master分支向wangbicong仓库的develop分支发起pull request请求
7. 等待wangbicong批改作业，如果有修改要求请在8.23之前完成

### 任务帮助

1. 遇到问题可以先Google，关键词`git` `github`
2. （可选）git可视化工具for mac：`Tower`

## 2. 学习markdown格式

> 2017.8.23       

### 任务步骤

1. 学习markdown的语法
2. 在`demo.md`用markdown的语法写一篇对markdown的整体介绍，包括但不限于以下问题：          
    - 为什么要使用markdown
    - markdown常见语法（此处不许偷懒，常见的必须都要涉及；不许复制粘贴，否则以后每天任务量翻倍）
      
### 任务帮助

1. 不同的工具对markdown格式的处理**略**有不同（注意黑体字）
2. 搜索关键词`markdown` `github markdown`
3. （可选）markdown编辑器for mac: `Typora`

## 3. 理解HTTP协议

> 2017.8.24       

### 任务步骤

1. 在`doc`目录下，建立`http.md`文件
2. 利用搜索引擎学习http协议，要求回答以下简单题并将答案写入`http.md`文件中：                  
    - 复制两段HTTP协议报文，要求分别为请求报文和响应报文
    - 请求报文的HTTP方法是什么，请对比两大HTTP方法的不同：GET和POST
    - 响应报文的HTTP状态码是什么，请简述1~5xx系列状态的作用，并从中选出你最有眼缘的两个status code，说明他们的作用
    - 请求报文和响应的报文的首部字段（headers）各是哪一段，从中选出你最有眼缘的两个字段，说明他们的作用和他们可能的取值与取值的含义

### 任务帮助

作为前端，要善用`Google Chrome`的开发者工具

## 4. HTTP协议的认证机制

> 2017.8.25 

### 任务步骤

1. 在`doc/http.md`里，回答以下简答题并将答案写入其中：                                  
    - 为什么说HTTP协议是无状态的                 
    - 无状态的HTTP协议下如何通过Cookie/Session来完成用户认证                
    - 请介绍`Basic Authentication`和`OAuth2`用户认证机制，要求说明其在HTTP协议报文中的位置               

## 5. Restful API

> 2017.8.26        

### 任务步骤

1. 在`doc`目录下，建立`restful.md`文件
2. 利用搜索引擎学习`Restful API`，要求回答以下简单题并将答案写入`restful.md`文件中：                  
    - `Restful API`是一种基于HTTP协议的API设计风格，请你说出其他几种API设计风格（说出两三个名词即可，无须介绍）          
    - `Restful API`中HTTP协议的四大方法`get` `post` `put` `delete`各表示什么             
    - `Restful API`中URL如何进行设计               
    - 为什么`/api/getBooks`这样的URL PATH不符合`Restful API`设计风格                     
    - 你认为用`Restful API`改写`/api/getBooks`后，有什么好处（可以结合对HTTP协议的理解）         
    
## 6. 初识Ingress

> 2017.8.27        

### 周末放假

小田同学最近事情比较多，严肃的王老师准备让小田同学周末休息一下，去把家附近广场的点都炸了！   

## 7. Github Restful API

> 2017.8.28       

### 任务步骤

1. 在`doc`目录下，建立`github-api.md`文件         
2. 打开[Github API](https://api.github.com/)，你会看到一系列关于Github的API。请尝试找到两个API，要求一个需要认证权限，另一个不需要认证权限
3. 在需要认证权限的API里，报错信息是什么，提示的帮助文档的URL是什么
4. 进入该帮助文档，在目录处找到`Authentication`一节，请使用自己的账号信息复现`Basic Authentication`和`OAuth2`认证
5. 使用已认证的方式去访问需要认证的URL
6. 将2~6步骤记录到`github-api.md`文件中

### 任务帮助

1. 在`chrome`里安装[json-formatter插件](https://chrome.google.com/webstore/detail/bcjindcccaagfpapjjmafapmmgkkhgoa)，可以方便查看json格式的数据         
2. 使用[Postman](https://www.getpostman.com)方便对API进行调试        
3. `curl`命令是`linux`下一款对`http`等协议高度封装的工具，实际上也只是把命令转换为协议本身，通过查阅`curl`文档即可知道各个子命令对`http`协议报文做了哪些操作

## 8. Npm与React环境搭建

> 2017.8.29        

### 任务步骤

1. 在`doc`下建立新文件夹`React`，用以记录所有`React`的学习笔记，在该文件夹下的`*.md`文件请以自己喜欢的方式命名。         
2. 在电脑上安装`npm`，介绍`npm`的基本作用和基本指令（至少包括`install` `uninstall`，需要学会使用`help`指令查询帮助）         
3. 使用`npm`安装在**全局位置**安装`create-react-app`后创建`React`项目，介绍`npm`包全局位置与本地位置的区别            
4. 运行你的项目，将运行后的网站截图展示出来（学习如何在`markdown`文件中使用相对路径引用图片，此处需要了解相对路径和绝对路径的不同）       


