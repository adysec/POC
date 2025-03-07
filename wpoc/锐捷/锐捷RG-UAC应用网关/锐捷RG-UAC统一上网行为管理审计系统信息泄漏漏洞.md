# 锐捷RG-UAC统一上网行为管理审计系统信息泄漏漏洞

# 一、漏洞简介
锐捷RG-UAC统一上网行为管理审计系统存在账号密码信息泄露,可以间接获取用户账号密码信息登录后台 。

# 二、影响版本
+ 锐捷RG-UAC统一上网行为管理审计系统

# 三、资产测绘
+ hunter`app.name="Ruijie 锐捷 RG-UAC"`
+ 登录页面

![1694194776421-ba24eefd-0902-408f-9b39-94df05de40a6.png](./img/kHsNEDmJ-KmEi_RV/1694194776421-ba24eefd-0902-408f-9b39-94df05de40a6-091037.png)

# 四、漏洞复现
1. `F12`搜索`super_admin`字段，发现`admin`账户和密码

![1694194847217-acaed4bc-eda4-4fae-a5ad-873559bc1694.png](./img/kHsNEDmJ-KmEi_RV/1694194847217-acaed4bc-eda4-4fae-a5ad-873559bc1694-341213.png)



> 更新: 2024-06-24 11:42:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vphzyvniletxc028>