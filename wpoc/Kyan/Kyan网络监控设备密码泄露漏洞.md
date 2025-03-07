# Kyan 网络监控设备密码泄露漏洞

# <font style="color:rgb(23, 46, 77);">一、漏洞简介</font>
Kyan网络监控设备存在账号密码泄露漏洞，该漏洞是由于开发人员将记录账户密码的文件放到网站目录，攻击者可通过访问目录获取Kyan网络监控设备账号密码，进入控制后台。

# 二、影响版本
+ Kyan 网络监控设备

# 三、资产测绘
+ hunter`app.name=="Kyan 网络监控设备"`
+ 特征

![1700735696467-ea2f2fba-f004-4687-a3f2-dfb3a2beaa8a.png](./img/Dvtz-ra2AXLF35Rp/1700735696467-ea2f2fba-f004-4687-a3f2-dfb3a2beaa8a-066628.png)

# 四、漏洞复现
```plain
/hosts
```

![1700735729224-68725e9b-5914-45cd-b997-a65cc83fa1fb.png](./img/Dvtz-ra2AXLF35Rp/1700735729224-68725e9b-5914-45cd-b997-a65cc83fa1fb-623104.png)

![1700735740516-f3d3ee66-1525-470f-aa0d-b35990866841.png](./img/Dvtz-ra2AXLF35Rp/1700735740516-f3d3ee66-1525-470f-aa0d-b35990866841-536015.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ph8dyaez8p98x1ah>