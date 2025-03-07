# Nacos Derby 远程命令执行漏洞(QVD-2024-26473)

# <font style="color:rgb(51, 51, 51);">一、漏洞简介</font>
<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。Nacos存在远程命令执行漏洞</font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">Nacos 2.3.2</font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ fofa `icon_hash="13942501"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/4dqBYlUSthO-Pvor/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-111429.png)

# 四、漏洞复现
前置条件：

```plain
1、需要naocs没有做鉴权，或者能登录后台获取凭证
2、需要使用的是derby数据库，如果是mysql就不行
```

准备3个文件

[exploit.py](https://www.yuque.com/attachments/yuque/0/2024/txt/29512878/1730102385434-bed3e0d1-f9aa-4fb0-97bf-58e02f1536a0.txt)[server.py](https://www.yuque.com/attachments/yuque/0/2024/txt/29512878/1730102385723-5c0ce8e6-955e-45d3-8edd-930373ebf091.txt)[config.py](https://www.yuque.com/attachments/yuque/0/2024/txt/29512878/1730102385874-06c45712-f176-431c-8a7e-aee74aa7a07e.txt)

1、修改config.py内容，host为自己的ip地址，port为自己电脑没有被占用的端口

```plain
server_host = '192.168.40.110'
server_port = 9999
```

2、然后直接运行命令python service.py 启动web服务，记住安装flask和requests的py模块

![1729316386052-7a74660b-9c2d-4bf8-9bf4-18d530e6d432.png](./img/4dqBYlUSthO-Pvor/1729316386052-7a74660b-9c2d-4bf8-9bf4-18d530e6d432-314080.png)

3、启动成功后，再运行python exploit.py，输入目标nacos地址即可执行命令

![1729316438195-42be8be8-5687-4574-98c1-09281b2c1d62.png](./img/4dqBYlUSthO-Pvor/1729316438195-42be8be8-5687-4574-98c1-09281b2c1d62-442473.png)

ping dnslog测试

![1729316528783-0d8ad515-f41b-4b4c-828d-f10beeeae9ad.png](./img/4dqBYlUSthO-Pvor/1729316528783-0d8ad515-f41b-4b4c-828d-f10beeeae9ad-630788.png)



> 更新: 2024-10-28 15:59:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dr4623v0c8wevsk2>