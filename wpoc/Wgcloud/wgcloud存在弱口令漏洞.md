# wgcloud 存在弱口令漏洞

# 一、漏洞简介
WGCLOUD设计思想为新一代极简运维监控系统，提倡快速部署，降低运维学习难度，全自动化运行，无模板和脚本。wgcloud 存在弱口令漏洞。

# 二、影响版本
+ WGCLOUD

# 三、资产测绘
+ hunter`app.name="WGCLOUD"`

# 四、漏洞复现
```plain
admin/111111
admin/admin123
admin/mall123
admin/promotion123
```

![1708917579157-caa7ef0c-2643-4a3c-8e1e-32f90e179071.png](./img/UvieiqQPBxxJVlH7/1708917579157-caa7ef0c-2643-4a3c-8e1e-32f90e179071-556641.png)

[wgcloud.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222141179-a4f038b2-589b-4f05-a78e-dbe4f397f14f.yaml)



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xgfgq2u0fd358i6o>