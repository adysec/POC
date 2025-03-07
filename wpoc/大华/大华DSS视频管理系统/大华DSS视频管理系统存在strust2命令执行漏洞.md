# 大华 DSS 视频管理系统 存在strust2命令执行漏洞

# 一、漏洞简介
大大华 DSS 视频管理系统 存在strust2命令执行漏洞，攻击者通过漏洞获取服务器权限。

# 二、影响版本
+ 大华 DSS 视频管理系统

# 三、资产测绘
+ hunter：`app.name=="Dahua 大华 DSS 视频管理系统"`

![1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc.png](./img/mc9SKA2jC6nV7nKC/1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc-976561.png)

+ 登录页面

![1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590.png](./img/mc9SKA2jC6nV7nKC/1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590-628349.png)

# 四、漏洞复现
漏洞地址

```java
/portal/login_init.action
```

[Strruts2全版本漏洞测试工具17-6过WAF版.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222238928-6658bffd-c0ae-4391-a18e-74f0966c3be6.jar)

![1701919580383-8d8fc9c5-c0a8-4d72-ae0b-8631dbf07114.png](./img/mc9SKA2jC6nV7nKC/1701919580383-8d8fc9c5-c0a8-4d72-ae0b-8631dbf07114-425195.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mg5fcbpsfxg6xgzl>