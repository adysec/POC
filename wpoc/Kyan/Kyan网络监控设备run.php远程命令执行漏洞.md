# Kyan 网络监控设备 run.php 远程命令执行漏洞

# 一、漏洞简介
Kyan 网络监控设备 run.php可在身份验证的情况下执行任意命令, 配合账号密码泄露漏洞，存在远程命令执行漏洞，可以获取服务器权限。

# 二、影响版本
+ Kyan 网络监控设备

# 三、资产测绘
+ hunter`app.name=="Kyan 网络监控设备"`
+ 特征

![1700735696467-ea2f2fba-f004-4687-a3f2-dfb3a2beaa8a.png](./img/koypSHLFpr1LdmCH/1700735696467-ea2f2fba-f004-4687-a3f2-dfb3a2beaa8a-230413.png)

# 四、漏洞复现
1. 通过Kyan 网络监控设备密码泄露漏洞登录系统后台

```plain
/hosts
```

![1700735729224-68725e9b-5914-45cd-b997-a65cc83fa1fb.png](./img/koypSHLFpr1LdmCH/1700735729224-68725e9b-5914-45cd-b997-a65cc83fa1fb-892875.png)

![1700735740516-f3d3ee66-1525-470f-aa0d-b35990866841.png](./img/koypSHLFpr1LdmCH/1700735740516-f3d3ee66-1525-470f-aa0d-b35990866841-768767.png)

2. 访问`run.php`,即可执行命令

```plain
/run.php
```

![1700735869217-7604bb3f-c59f-4273-aa02-9a842732a8ab.png](./img/koypSHLFpr1LdmCH/1700735869217-7604bb3f-c59f-4273-aa02-9a842732a8ab-341331.png)

![1700735883989-6c9eab4c-8cfb-4276-865c-d7aa6f0c92c7.png](./img/koypSHLFpr1LdmCH/1700735883989-6c9eab4c-8cfb-4276-865c-d7aa6f0c92c7-578727.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/un5hy49hzv7rnell>