# 荷花商品混凝土ERP系统DictionaryEdit.aspx 页面存在SQL注入

# 一、漏洞简介
杭州荷花软件有限公司开发的商混ERP系统。这套系统主要是处理建筑公司或者各项工程的搅拌站管理，内部含有销售模块、生产管理模块、实验室模块、人员管理等，该公司的商品混凝土ERP系统/Sys/DictionaryEdit.aspx处dict_key参数存在SQL报错注入漏洞，攻击者可通过该漏洞获取数据库权限。

# 二、影响版本
+ 荷花商品混凝土ERP系统

# 三、资产测绘
+ hunter`app.name=="荷花商品混凝土ERP系统"`
+ 特征

![1700038673461-c08709af-de7f-4bcf-b3c8-aa5dda30d94b.png](./img/J81dH0tJ3we7JtSC/1700038673461-c08709af-de7f-4bcf-b3c8-aa5dda30d94b-115449.png)

# 四、漏洞复现
```plain
/Sys/DictionaryEdit.aspx?dict_key=1
```

出现如下页面大概率存在该漏洞

![1700038780840-29a40f07-46cc-42c4-a145-2e84c2f63ca8.png](./img/J81dH0tJ3we7JtSC/1700038780840-29a40f07-46cc-42c4-a145-2e84c2f63ca8-492785.png)

sqlmap

![1700038797493-de6b792b-3f04-4aa0-aeb7-6008e0cc67d9.png](./img/J81dH0tJ3we7JtSC/1700038797493-de6b792b-3f04-4aa0-aeb7-6008e0cc67d9-532453.png)



> 更新: 2024-02-29 23:55:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zf12hiwuxxr5b0hp>