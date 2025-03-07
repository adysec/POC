# Nacos存在默认口令漏洞

# 一、漏洞简介
<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。Nacos存在默认口令漏洞。</font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">Nacos </font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/-rSL8iMmnJh02-2S/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-132632.png)

# 四、漏洞复现
```plain
nacos/nacos
```

![1706100637966-94b887f6-0514-4248-ae6a-37c5dae60015.png](./img/-rSL8iMmnJh02-2S/1706100637966-94b887f6-0514-4248-ae6a-37c5dae60015-323211.png)



> 更新: 2024-10-28 15:59:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sfeezle5mv21kuf2>